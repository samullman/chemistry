<script lang="ts">
	import { writable } from 'svelte/store';

	let flower: HTMLElement;
	let coords = writable({ x: 50, y: 50 });

	function updatePos(e: any) {
		coords.set({ x: e.clientX, y: e.clientY });

		flower.style.top = e.clientY + 'px';
		flower.style.left = e.clientX + 'px';
	}
</script>

<div class="hero">
	<h1>Peace of mind:</h1>

	<div class="items">
		<div class="item">
			<h2>Product</h2>

			Websites, Apps, Ecommerce
		</div>
		<div class="item">
			<h2>Engineering</h2>

			React, Svelte, Web3
		</div>
		<div class="item">
			<h2>Growth</h2>

			Sales, Marketing, Relationships
		</div>
	</div>

	<img
		draggable="false"
		bind:this={flower}
		src="/flower.png"
		alt="flower"
		class="flower"
		height={120}
		width={120}
	/>
</div>

<style lang="scss">
	.hero {
		margin-top: 4rem;
		min-height: calc(100vh - 8rem);
		display: flex;
		padding: 1rem;
		align-items: center;
		justify-content: center;
		user-select: none;
		flex-direction: column;

		h1 {
			font-size: 2.1rem;
			font-weight: bold;
			margin-bottom: 1rem;
		}

		.items {
			display: flex;
			gap: 1rem;
			margin: 1.2rem auto;
			flex-wrap: wrap;
			justify-content: center;

			.item {
				padding: 1.5rem;
				max-width: 20rem;
				font-size: 0.9rem;
				border: 3px dashed black;
				border-radius: 0.75rem;

				h2 {
					font-size: 1.5rem;
					margin-bottom: 0.5rem;
					text-align: center;
				}
			}
		}

		.flower {
			transition: 1.5s ease;
		}

		.flower:active {
			transform: rotate(560deg);
		}
	}
</style>
