<script>
	export let reverse;
</script>

<nav class:reverse>
	<h3>
		<a href="/">samullman.com</a>
	</h3>
	<ul>
		<li><a href="/about">about</a></li>
		<li><a href="/ui">ui</a></li>
		<li><a href="/writing">writing</a></li>
		<li><a href="/learning">learning</a></li>
	</ul>
</nav>

<style lang="scss">
	nav {
		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
		padding: 1rem;
		width: 100%;
		margin: 0 auto;
		box-sizing: border-box;

		h3 {
			margin-bottom: 0.5rem;
		}

		&.reverse {
			flex-direction: column-reverse;

			h3 {
				margin-top: 0.5rem;
			}

			ul {
				flex-direction: row-reverse;
			}
		}
	}

	h3 {
		font-size: 1.3rem;
	}

	ul {
		list-style: none;
		display: flex;
		justify-content: flex-end;
		align-items: center;
		gap: 1rem;
		font-size: 1.2rem;
		margin: 0;
		padding-left: 0;
	}

	a {
		text-decoration: none;
		color: black;

		&:hover {
			opacity: 0.6;
		}
	}
</style>
