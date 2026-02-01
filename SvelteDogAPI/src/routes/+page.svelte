<script>
	import { goto } from "$app/navigation";

	let raca = ""

	async function buscandoCachorro() {

		if (!raca.trim()) return
		goto(`/resultadoBusca/${raca.toLowerCase().replace(' ', '-')}`)
	}

	function pesquisarAoPressionarTeclaEnter(e) {
		if (e.key === "Enter") {
			buscandoCachorro()
		}
	}
</script>

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Comfortaa:wght@300..700&display=swap" rel="stylesheet">

<main>
	<img src="/src/img/buscaDogLogo.png"
	alt="logo"
	id="logo"
	/>

	<div class="busca">
		<input
			type="text"
			id="input"
			placeholder="Busque a raça do cachorro"
			bind:value={raca}
			on:keydown={pesquisarAoPressionarTeclaEnter}
		/>

		<img
			src="/src/img/Search.svg"
			alt="icone de busca"
			id="iconeBusca"
			on:click={buscandoCachorro}
		/>
	</div>
</main>

<style>
	main {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		height: 100vh;
	}

	#logo{
		height: 110px;
	}

	.busca {
		position: relative;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	#iconeBusca {
		position: absolute;
		right: 0;
		padding: 10px;
		height: 25px;
	}

	input {
		width: 60vh;
		height: 40px;
		border-radius: 20px;
		border: none;
		text-align: center;
		font-style: italic;
		background-color: antiquewhite;
	}

</style>
