<script>
	import '../app.css';

	let { children } = $props();
</script>

<div class="app">

	<main>
		{@render children()}
	</main>

	<footer>
		<p>
			made bij miro matton <a href="https://miromatton.be">have a looksie :)</a>
		</p>
	</footer>
</div>

<style>
	.app {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
	}

	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		padding: 1rem;
		width: 100%;
		max-width: 120rem;
		margin: 5rem auto;
		box-sizing: border-box;
	}

	footer {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		padding: 12px;
	}

	footer a {
		font-weight: bold;
	}

	@media (min-width: 480px) {
		footer {
			padding: 12px 0;
		}
	}
</style>
