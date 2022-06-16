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
	export let subject;
	export let chapter;
</script>

<a href={'/' + subject}> Back </a>

{subject}
{chapter}
