<script lang="ts">
	import { page } from '$app/stores';
	import Modal from './modal.svelte';
	import { onMount } from 'svelte';

	function toggleModal() {
		open = !open;
	}

	let open = false;

	const links = [
		{
			title: 'Home',
			path: '/'
		},

		// {
		// 	title: 'Projects',
		// 	path: '/projects'
		// },

		{
			title: 'About',
			path: '/about'
		},

		// {
		// 	title: 'Services',
		// 	path: '/services'
		// },

		// {
		// 	title: 'UI',
		// 	path: '/ui'
		// },

		// {
		// 	title: 'Writing',
		// 	path: '/writing'
		// },

		// {
		// 	title: 'Learning',
		// 	path: '/learning'
		// },

		{
			title: 'Contact',
			path: '/contact'
		}
	];
</script>

<header>
	<nav>
		<h3 class="title">
			<a href="/" class:active={$page.url.pathname === '/'}>{$page.url.host}</a>
		</h3>

		<button on:click={toggleModal}> Sitemap </button>
	</nav>
</header>

<div class="drawer">
	<div class:open>
		<div class="sitemap">
			<ul>
				{#each links as link}
					<div on:click={toggleModal}>
						<a href={link.path} class:active={$page.url.pathname === link.path}>
							<li>
								{link.title}
							</li>
						</a>
					</div>
				{/each}
			</ul>
		</div>
	</div>
</div>

<div class="cupertino-pane">
	<h3>Sitemap</h3>
</div>

<style lang="scss">
	// .cupertino-pane-wrapper .pane {
	// 	width: 100vw !important;
	// 	max-width: none !important;
	// 	border-radius: none !important;
	// }

	.drawer {
		& > div {
			position: fixed;
			bottom: 0;
			width: 100vw;
			background: #ffffff;
			backdrop-filter: blur(5px);
			height: 0px;
			box-sizing: border-box;
			transition: height 0.4s ease, opacity 0.4s ease, box-shadow 0.4s ease;
			opacity: 0;
			z-index: 1000;

			&.open {
				height: 80vh;
				box-shadow: 0 0 1rem 0.5rem #cccccc66;
				opacity: 1;
			}

			.sitemap {
				padding: 2rem 1rem;
				max-width: 32rem;
				margin: 0 auto;

				ul {
					list-style: none;
					display: flex;
					gap: 1rem;
					font-size: 1.2rem;
					margin: 0;
					padding-left: 0;
					flex-wrap: wrap;
					overflow: scroll;

					$colors: (
						'/': var(--red),
						'/about': var(--turqoise),
						'/ui': var(--dark-yellow),
						'/learning': var(--green),
						'/writing': var(--purple),
						'/projects': var(--blue),
						'/contact': var(--blue)
					);

					@each $path, $color in $colors {
						a[href='#{$path}'] {
							&:hover {
								color: $color;

								li {
									border-color: $color;
								}
							}
						}
					}

					& > div {
						flex: calc(50% - 0.5rem);

						@media screen and (max-width: 36rem) {
							flex: 100%;
						}
					}

					a {
						display: block;

						text-decoration: none;
						color: black;
						height: 100%;
						width: 100%;
						transition: all 0.2s ease;

						&:active {
							transform: scale(0.98);
						}
					}

					li {
						padding: 2.5rem 2rem;
						border: 0.2rem dashed black;
						box-sizing: border-box;
						background: #ffffffdd;
						backdrop-filter: blur(5px);
						border-radius: 1rem;
						transition: border-color 0.2s ease;
						text-align: center;
						cursor: pointer;
					}
				}
			}
		}
	}

	.cupertino-pane {
		padding: 2em;
		display: none;
	}

	header {
		position: fixed;
		width: 100vw;
		top: 0;
		left: 0;
		background: #ffffff;
		backdrop-filter: blur(5px);
		z-index: 2000;
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
	}

	h3.title {
		font-size: 1.3rem;
		margin-bottom: 0.5rem;
		margin-top: 0.5rem;
	}
</style>
