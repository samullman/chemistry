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

	const subjects = [
		{
			title: 'Math',
			url: '/math'
		},

		{
			title: 'Chemistry',
			url: '/chemistry'
		},

		{
			title: 'Physics',
			url: '/physics'
		},

		{
			title: 'Biology',
			url: '/biology'
		},

		{
			title: 'Computer Science',
			url: '/computer-science'
		}
	];
</script>

<svelte:head>
	<title>Learning</title>
</svelte:head>

<h1>Learning</h1>
<div>The program.</div>

<div class="subjects">
	{#each subjects as subject}
		<h2>
			<a href={'/' + path + subject.url}>{subject.title}</a>
		</h2>
	{/each}
</div>

<!-- recognize state of spirit, loving state of being, understanding state of mind -->
<style lang="scss">
	.subjects {
		text-align: center;
		margin: 1rem 0;
		display: flex;
		flex-direction: column;
		gap: 1rem;
	}

	h2 {
		margin-bottom: 0;
		font-size: 1.2rem;
	}
</style>
