<script context="module">
	export async function load({ params }) {
		return {
			props: {
				atom: params.slug
			}
		};
	}
</script>

<script>
	export let atom;
	import Layout from '$lib/components/layout.svelte';
	import atoms from '$lib/atoms.json';
	import Atom from '$lib/components/atom.svelte';

	const key = atom;
	const value = atoms[key];
</script>

<Layout>
	<h2>{value.name}</h2>
	<Atom {key} {value} />
	<br />

	<div class="element">
		<div class="shell">
			{#each value.shells as shell, i}
				<div class="valence">
					{#each Array(shell) as _}
						<span class="valence-electron" />
					{/each}
				</div>
			{/each}
		</div>

		<p>
			<a href={value.source} target="_blank"> Source </a>
		</p>

		<p>
			{value.summary}
		</p>

		<img src={value.spectral_img} class="spectra" loading="lazy" />

		<!-- <p>
				<img
					src={value.crystalStructure}
					alt={value.crystal}
					class="crystal-structure"
					loading="lazy"
				/>
			</p> -->
	</div>
</Layout>

<style lang="scss">
	h2 {
		font-size: 2em;
		margin-top: 0;
	}

	.element {
		margin-bottom: 2em;
	}

	.number {
		font-size: 2em;
	}
	.title {
		display: flex;
		justify-content: space-between;
	}

	.shell {
		margin-bottom: 1em;
	}

	p {
		margin-top: 0;
	}

	.stats {
		display: flex;
		gap: 0.5em;
	}

	.valence {
		display: flex;
		gap: 0.5em;
		margin-bottom: 0.25em;

		.valence-electron {
			width: 0.5em;
			height: 0.5em;
			border-radius: 50%;
			background-color: #000;
		}
	}

	.spectra {
		width: 100%;
		height: 5em;
		border-radius: 0.5em;
	}

	.crystal-structure {
		width: 6em;
	}
</style>
