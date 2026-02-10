<script lang="ts">
	import '$lib/style.css';

	import love from '$lib/assets/love.svg';
	import Form from '$lib/components/Form.svelte';
</script>

<main>
	<header>
		<img class="logo-img" src={love} alt="Un dibujo de una flecha atravezando una carta." />
		<h1>Correo Correo</h1>
	</header>
	<Form />
</main>

<style>
	:global(body) {
		display: flex;
		width: 100vw;
		height: 100vh;

		justify-content: center;
		align-content: center;
	}

	.logo-img {
		width: 6ch;
	}

	h1 {
		font-size: inherit;
		font-style: italic;
		font-weight: inherit;
	}

	header {
		opacity: 70%;
	}

	main {
		display: flex;
		flex-direction: column;
		justify-content: center;

		gap: 0.5em;
		width: 70%;
		min-width: 0;
	}
</style>
