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
	<h1 class="title">Developing for a better tomorrow.</h1>

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
		height: calc(100vh);
		width: 100vw;
		width: 100%;
		position: relative;

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
		height: calc(100vh - 4rem);
		display: flex;
		padding: 1rem;
		align-items: center;
		justify-content: center;
		user-select: none;
		flex-direction: column;

		.title {
			padding: 1.5rem;
			max-width: 20rem;
			font-size: 2rem;
			border: 3px dashed black;
			border-radius: 0.75rem;
		}

		.flower {
			transition: 1.5s ease;
		}

		.flower:active {
			transform: rotate(560deg);
		}
	}
</style>
