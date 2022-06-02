<script context="module">
	export async function load({ routeId }) {
		return {
			props: {
				path: routeId
			}
		};
	}
</script>

<script>
	export let path;
	import Header from '$lib/components/header.svelte';
	import '../app.css';
</script>

<Header />

<main>
	<div class={'boxed ' + path}>
		<slot />
	</div>
</main>

<Header reverse />

<style lang="scss">
	$colors: (
		'home': #e74c3c,
		'about': #3498db,
		'ui': #f1c40f,
		'learning': #27ae60,
		'writing': #8e44ad
	);

	.boxed {
		border: 2px dashed;
		border-radius: 1em;
		padding: 1.2em;

		@each $path, $color in $colors {
			&.#{$path} {
				border-color: $color;

				:global(a) {
					color: $color !important;

					&:hover {
						opacity: 0.6;
					}
				}

				:global(h1) {
					color: $color !important;
				}
			}
		}
	}

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
