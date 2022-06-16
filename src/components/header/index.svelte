<script>
	import { page } from '$app/stores';
	import Modal from './modal.svelte';

	export let reverse;

	const links = ['about', 'ui', 'writing', 'learning'];
</script>

<header class:reverse>
	<nav class:reverse>
		<h3>
			<a href="/" class:active={$page.url.pathname === '/'}>samullman.com</a>
		</h3>
		<ul>
			{#each links as link}
				<li>
					<a href={'/' + link} class:active={$page.url.pathname === '/' + link}>{link}</a>
				</li>
			{/each}

			<li>
				<Modal />
			</li>
		</ul>
	</nav>
</header>

<style lang="scss">
	header {
		position: fixed;
		width: 100vw;
		top: 0;
		left: 0;
		background: #ffffff77;
		backdrop-filter: blur(10px);
		z-index: 2000;

		&.reverse {
			position: relative;
		}
	}

	nav {
		display: flex;
		user-select: none;
		justify-content: space-between;
		align-items: center;
		padding: 1rem;
		width: 100%;
		max-width: 52rem;
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

	$colors: (
		'/': #e74c3c,
		'/about': #3498db,
		'/ui': #f1c40f,
		'/learning': #27ae60,
		'/writing': #8e44ad
	);

	@each $path, $color in $colors {
		a[href='#{$path}'].active {
			// color: $color;
			text-decoration: underline;
		}
	}
</style>
