<script>
	import { writable } from 'svelte/store';

	let flower;
	let coords = writable({ x: 50, y: 50 });
	let size = writable(80);

	function updatePos(e) {
		coords.set({ x: e.clientX, y: e.clientY });

		flower.style.top = e.clientY + 'px';
		flower.style.left = e.clientX + 'px';
	}
</script>

<div class="hello">
	<h1>Developing for a better tomorrow.</h1>
</div>

<div
	class="hero"
	on:mousemove={updatePos}
	on:mousedown={() => size.set(50)}
	on:mouseup={() => size.set(50)}
>
	<img
		draggable="false"
		bind:this={flower}
		src="/flower.png"
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
			transition: transform 1.2s ease;
			top: calc(50% - 40px);
			left: calc(50% - 40px);
		}
	}

	.hello {
		position: fixed;
		width: 100vw;
		height: calc(100vh - 4rem);
		display: flex;
		align-items: center;
		justify-content: center;

		h1 {
			font-size: 2rem;
		}
	}
</style>
