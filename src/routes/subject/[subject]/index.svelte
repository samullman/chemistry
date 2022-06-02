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
	import Layout from '$lib/components/layout.svelte';
	import Math from '$lib/components/pages/math.svelte';
	import Chemistry from '$lib/components/pages/chemistry.svelte';
	export let subject;
</script>

<Layout>
	{#if subject === 'math'}
		<Math />
	{:else if subject === 'chemistry'}
		<Chemistry />
	{/if}
</Layout>
