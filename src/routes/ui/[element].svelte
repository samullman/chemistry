<script context="module">
	export function load({ params }) {
		debugger;
		return {
			props: {
				element: params.element
			}
		};
	}
</script>

<script>
	import DataViz from '$lib/components/ui/data-viz.svelte';
	export let element;
</script>

{#if element === 'data-viz'}
	<DataViz />
{:else if element === 'chemistry'}
	akdjsnf
{/if}
