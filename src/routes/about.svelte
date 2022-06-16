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

<!-- recognize state of spirit, loving state of being, understanding state of mind -->
<style lang="scss">
	.bio {
		display: flex;
		flex-wrap: wrap;
		gap: 1.6rem;
		font-size: 1.2rem;

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
