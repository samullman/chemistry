<script context="module">
	export function load({ params }) {
		return {
			props: {
				subject: params.subject,
				chapter: params.chapter
			}
		};
	}
</script>

<script>
	import Layout from '$lib/components/layout.svelte';
	export let subject;
	export let chapter;
</script>

<Layout>
	<a href={"/" + subject}>
		Back
	</a>
	
	{subject}
	{chapter}
</Layout>
