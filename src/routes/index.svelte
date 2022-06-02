<script>
	import Layout from '$lib/components/layout.svelte';
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<Layout>Home</Layout>

<!-- recognize state of spirit, loving state of being, understanding state of mind -->
<style lang="scss">
	.element {
		margin-bottom: 2em;
	}
	.title {
		display: flex;
		justify-content: space-between;
	}

	.shell {
		margin-bottom: 1em;
	}

	p {
		margin-top: 0;
	}

	.stats {
		display: flex;
		gap: 0.5em;
	}

	.valence {
		display: flex;
		gap: 0.5em;
		margin-bottom: 0.25em;

		.valence-electron {
			width: 0.5em;
			height: 0.5em;
			border-radius: 50%;
			background-color: #000;
		}
	}

	.spectra {
		width: 100%;
		height: 5em;
		border-radius: 0.5em;
	}

	.crystal-structure {
		width: 6em;
	}
</style>
