<script context="module">
	export function load({ params }) {
		return {
			props: {
				subject: params.subject
			}
		};
	}
</script>

<script>
	import Math from '$lib/components/pages/math.svelte';
	import Chemistry from '$lib/components/pages/chemistry.svelte';
	export let subject;
</script>

{#if subject === 'math'}
	<Math />
{:else if subject === 'chemistry'}
	<Chemistry />
{/if}
