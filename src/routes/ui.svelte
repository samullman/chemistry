<script>
	const elements = [
		{
			title: 'Charts & Data Viz',
			slug: 'data-viz'
		},

		{
			title: 'Carousel',
			slug: 'carousel'
		},

		{
			title: 'Media',
			slug: 'media'
		},

		{
			title: 'World',
			slug: 'world'
		}
	];
</script>

<svelte:head>
	<title>UI</title>
</svelte:head>

<h1>UI</h1>
<div class="subtitle">Let's build an app!</div>

<div class="elements">
	{#each elements as element}
		<div>
			<h2>
				<a href={'/ui/' + element.slug}>{element.title}</a>
			</h2>
		</div>
	{/each}
</div>

<!-- recognize state of spirit, loving state of being, understanding state of mind -->
<style lang="scss">
	.subtitle {
		text-align: center;
	}

	.elements {
		text-align: center;
		margin: 1rem 0;
		display: flex;
		flex-wrap: wrap;
		gap: 1rem;

		& > div {
			flex: calc(50% - 1rem);
		}

		h2 {
			margin-bottom: 0;
			font-size: 1.2rem;
		}
	}
</style>
