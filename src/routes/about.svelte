<svelte:head>
	<title>About</title>
</svelte:head>

<h1 style="opacity:0;position:absolute;">About</h1>

<div class="bio page">
	<div>
		<img src="/crossed-arms.png" />
	</div>

	<div>
		<div>Born and raised in Portland, OR, USA.</div>

		<div>
			Currently helping businesses and organizations develop systems and technology out of Austin,
			TX, USA.
		</div>

		<p>Seven years of experience developing technology for agencies, individuals, and startups.</p>

		<p>Based in Austin, TX.</p>
	</div>
</div>

<!-- recognize state of spirit, loving state of being, understanding state of mind -->
<style lang="scss">
	.bio {
		display: flex;
		flex-wrap: wrap;
		gap: 2rem;
		font-size: 1.2rem;
		@media screen and (max-width: 32rem) {
			flex-direction: column;
		}

		& > div {
			flex: 1;
		}

		img {
			width: 100%;
			border-radius: 0.75rem;
		}
	}
</style>
