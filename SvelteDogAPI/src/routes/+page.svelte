<script>
	import { onMount } from "svelte";

	async function buscandoCachorro() {
		const input = document.getElementById("input").value;

		const url = `https://dog.ceo/api/breeds/{$input}/image`;

		const response = await fetch(url);
		const dados = await response.json();
	}
</script>

<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link href="https://fonts.googleapis.com/css2?family=Poetsen+One&display=swap" rel="stylesheet"
/>

<main>
	<h1>Busca Dog</h1>

	<div class="busca">
		<input type="text" id="input" placeholder="Busque a raça do cachorro"/>

			<img src="/src/img/Search.svg" alt="icone de busca" id="botaoBusca">

	</div>

	


</main>

<style>
	main {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		background-color: bisque;
		height: 100vh;
	}

	h1 {
		color: rgb(172, 0, 66);
		font-family: 'Poetsen One';
	}

	.busca{
		position: relative;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	#botaoBusca{
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
	}
</style>
