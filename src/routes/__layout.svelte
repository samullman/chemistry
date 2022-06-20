<script context="module">
	export async function load({ routeId }) {
		return {
			props: {
				path: routeId || 'home'
			}
		};
	}
</script>

<script>
	import { page } from '$app/stores';

	export let path;

	import Header from '$lib/components/header/index.svelte';
	import '../app.css';
</script>

<Header />

<main>
	<div class="page">
		<slot />
	</div>
</main>

<style lang="scss">
	// .boxed {
	// 	border: 2px dashed;
	// 	border-radius: 1em;
	// 	padding: 1.2em;
	// }

	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		align-items: center;
		width: 100%;
		box-sizing: border-box;
	}
</style>
