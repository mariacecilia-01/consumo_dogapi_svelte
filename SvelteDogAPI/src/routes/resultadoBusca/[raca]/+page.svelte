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

<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link
    href="https://fonts.googleapis.com/css2?family=Comfortaa:wght@300..700&display=swap"
    rel="stylesheet"
/>

<main>
    <div class="cabecalho">
        <h1>
            Resultados para sua busca
            <span class="fundoColorido">"{raca}"</span>
        </h1>

        <img
            src="/src/img/casa.png"
            alt="casa"
            id="voltar"
            on:click={voltarPaginaInicial}
        />
    </div>

    {#if erro}
        <p>{erro}</p>
    {:else}
        <div class="layout">
            {#each imagens as img}
                <img src={img} alt="Cachorro {raca}" loading="lazy" />
            {/each}
        </div>
    {/if}
</main>

<style>
    main {
        font-family: "Comfortaa";
        padding: 1rem;
        text-align: center;
        background: #f5f5f5;
        max-height: 100vh;
    }

    .cabecalho {
        display: flex;
        align-items: center;
        justify-content: center;
        position: relative;
    }

    .cabecalho img {
        position: absolute;
        right: 0;
        height: 50px;
        cursor: pointer;
    }

    .cabecalho img:hover {
        transform: scale(1.1);
        transition: transform 0.3s ease;
    }

    h1 {
        margin: 1.5rem;
    }

    .fundoColorido {
        background-color: #ffeb3b;
        padding: 0.2rem 0.4rem;
        border-radius: 4px;
        color: #000;
        font-weight: bold;
    }

    .fundoColorido:hover {
        box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
        transition: box-shadow 0.3s;
    }

    .layout {
        column-count: 5;
        column-gap: 1rem;
    }

    .layout img {
        width: 100%;
        margin-bottom: 1rem;
        border-radius: 12px;
        display: block;
    }

    img:hover {
        transform: scale(1) rotate(-3deg);
        transition: transform 0.3s ease;
    }
</style>
