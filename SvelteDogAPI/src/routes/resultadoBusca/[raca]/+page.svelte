<script>
    import { onMount } from "svelte";
    import { goto } from "$app/navigation";

    export let params;
    let raca = params.raca;

    let imagens = [];
    let erro = null;

    onMount(async () => {
        try {
            const racaUrl = raca.toLowerCase().replace(" ", "-");

            const response = await fetch(
                `https://dog.ceo/api/breed/${racaUrl}/images`,
            );
            const dados = await response.json();

            if (dados.status === "success") {
                imagens = dados.message;
            } else {
                erro = "Raça não encontrada";
            }
        } catch {
            erro = "Erro ao buscar imagens";
        }
    });

    function voltarPaginaInicial() {
        goto("/");
    }
</script>

<main>
    <h1>Resultados para sua busca: {raca}</h1>

    {#if erro}
        <p>{erro}</p>
    {:else}
        <div class="grid-imagens">
            {#each imagens as img}
                <img src={img} alt="Cachorro {raca}" />
            {/each}
        </div>
    {/if}

    <button class="voltar" on:click={voltarPaginaInicial}> Voltar </button>
</main>

<style>
    main {
        font-family: "Poetsen One", sans-serif;
        padding: 2rem;
        text-align: center;
        background: #f5f5f5;
        min-height: 100vh;
    }

    h1 {
        margin-bottom: 1.5rem;
        color: #333;
    }

    .grid-imagens {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
        gap: 1rem;
        margin-bottom: 2rem;
    }

    .grid-imagens img {
        width: 100%;
        border-radius: 10px;
        box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
    }

    .voltar {
        padding: 0.8rem 1.5rem;
        font-size: 1rem;
        border: none;
        border-radius: 5px;
        background: #ff6b6b;
        color: white;
        cursor: pointer;
        transition: background 0.2s;
    }

    .voltar:hover {
        background: #ff4757;
    }
</style>
