<script>
	const history = [
		{
			title: '1906',
			link: 'https://1906newhighs.com/',
			image: '/history/1906.png'
		},

		{
			title: 'Applied Materials',
			link: 'https://www.appliedmaterials.com/interactive-proxy/',
			image: '/history/applied.png'
		},

		{
			title: 'Code Nation',
			link: 'https://codenation.org/',
			image: '/history/code-nation.png'
		},

		{
			title: 'Marinade Finance',
			link: 'https://marinade.finance/',
			image: '/history/marinade.png'
		},

		{
			title: 'Munchery',
			link: 'https://munchery.com/',
			image: '/history/munchery.png'
		},

		{
			title: 'Orbit Exchance',
			link: 'https://www.orbitexchange.io/',
			image: '/history/orbit.png'
		},

		{
			title: 'Titan Analytics',
			link: 'https://blockchaingaminganalytics.com/',
			image: '/history/titan.png'
		}
	];
</script>

<svelte:head>
	<title>About</title>
</svelte:head>

<h1 style="opacity:0;position:absolute;">About</h1>

<div class="bio">
	<div>
		<img src="/crossed-arms.png" />
	</div>

	<div>
		<h2>Sam Ullman</h2>
		<p>I was born and raised in Portland, OR, USA.</p>

		<p>
			I attended Claremont McKenna College and nearly became a doctor before transitioning into tech
			in 2015.
		</p>

		<p>
			Currently – I am working with startups and various tech organizations to develop cutting-edge
			UI/UX and integrated web technology.
		</p>

		<p>
			I have seven years of experience working across the stack on product, growth, and communities.
		</p>

		<p>Based in Austin, TX, USA.</p>

		<p>🤠</p>
	</div>
</div>

<div>
	<h2>Past Work</h2>

	<div class="history">
		{#each history as item}
			<a href={item.link} class="item" target="_blank">
				<img src={item.image} />

				<div class="title">
					<h3>
						{item.title}
					</h3>
				</div>
			</a>
		{/each}
	</div>
</div>

<!-- recognize state of spirit, loving state of being, understanding state of mind -->
<style lang="scss">
	.history {
		display: flex;
		flex-wrap: wrap;
		gap: 1rem;

		.item {
			color: black;
			flex: calc(50% - 1rem);
			transition: 0.2s all ease;

			&:active {
				transform: scale(0.98);
			}

			img {
				width: 100%;
				object-fit: cover;
				border: 2px dashed black;
				border-radius: 0.5rem;
				box-sizing: border-box;
				min-height: 15rem;
			}

			.title {
				padding: 0.25rem 0.75rem;
			}
		}
	}
	.bio {
		margin-bottom: 1rem;
		display: flex;
		flex-wrap: wrap;
		gap: 1.6rem;
		font-size: 1.15rem;

		@media screen and (max-width: 36rem) {
			flex-direction: column;
		}

		& > div {
			box-sizing: border-box;
			flex: 1;
		}

		img {
			width: 100%;
			max-width: 31rem;
			object-fit: cover;

			border-radius: 0.75rem;
		}

		h2 {
			margin-bottom: 1rem;
		}
	}
</style>
