<script>
	import Header from './header.svelte';
	import '../../app.css';
</script>

<Header />

<main>
	<slot />
</main>

<Header />

<style>
	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		padding: 0 1rem;
		width: 100%;
		max-width: 1024px;
		margin: 0 auto;
		box-sizing: border-box;
	}

	footer {
		display: flex;
		flex-direction: column;
	}
</style>
