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

<div class="hello">
	<h1>Developing for a better tomorrow.</h1>
</div>

<div class="hero" on:mousemove={updatePos}>
	<img
		draggable="false"
		bind:this={flower}
		src="/flower.png"
		alt="flower"
		class="flower"
		height={80}
		width={80}
	/>
</div>

<style lang="scss">
	.hero {
		height: calc(100vh);
		width: 100vw;
		width: 100%;
		position: relative;

		&:active {
			.flower {
				transform: translate(-50%, -50%) rotate(560deg);
			}
		}

		.flower {
			user-select: none;
			position: absolute;
			transform: translate(-50%, -50%) rotate(0);
			transition: transform 1.2s ease, top 0.2s linear, left 0.2s linear;
			top: calc(50% - 30px);
			left: calc(50% - 0px);
		}
	}

	.hello {
		position: fixed;
		width: 100vw;
		height: calc(100vh - 4rem);
		display: flex;
		align-items: center;
		justify-content: center;
		user-select: none;

		h1 {
			font-size: 2rem;
		}
	}
</style>
