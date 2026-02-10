<script lang="ts">
	let code = $state('');
	let inputValid = $derived(cleanCode(code).length === 6 && /^[A-Za-z0-9]{6}$/.test(code));
	let buttonDisabled = $derived(!inputValid);

	function cleanCode(code: string) {
		return code.replace(/\s+/g, '');
	}
	function processButtonClick() {
		window.location.href = `https://alii.fillout.com/correocorreo?code=${cleanCode(code)}`;
	}
</script>

<div class="form">
	<p>Envíale una carta de San Valentín a quien quieras. Pon tu código abajo:</p>
	<label for="code-input"></label>

	<span class="input-button-block">
		<input
			type="text"
			id="code-input"
			placeholder="ABC123"
			bind:value={code}
			bind:this={inputElement}
		/>
		<button disabled={buttonDisabled} onclick={processButtonClick}>Continuar</button>
	</span>
</div>

<style>
	.form {
		display: flex;
		flex-direction: column;
		gap: 0.2em;

		width: 100%;
	}

	.form p {
		max-width: 80ch;
	}

	.input-button-block {
		font-size: 1rem;
		display: flex;
		gap: 0.5em;
	}

	input {
		border: solid var(--color-main) 1pt;
		border-radius: 3pt;
		padding: 1ch;
		font-family: monospace;
		text-transform: uppercase;
	}

	button {
		border-radius: 3pt;
		background-color: var(--color-main);
		color: var(--color-contrast);
		padding: 1ch;
		cursor: pointer;
	}

	button:disabled {
		opacity: 50%;
		cursor: default;
	}
</style>
