<script>
	import atoms from '$lib/atoms.json';
	import Atom from '$lib/components/atom.svelte';
	let per1 = Object.entries(atoms).filter(([key, value]) => {
		return value.period == 1;
	});

	let per2 = Object.entries(atoms).filter(([key, value]) => {
		return value.period == 2;
	});

	let per3 = Object.entries(atoms).filter(([key, value]) => {
		return value.period == 3;
	});

	let per4 = Object.entries(atoms).filter(([key, value]) => {
		return value.period == 4;
	});

	let per5 = Object.entries(atoms).filter(([key, value]) => {
		return value.period == 5;
	});

	let per6 = Object.entries(atoms).filter(([key, value]) => {
		return value.period == 6;
	});

	let per7 = Object.entries(atoms).filter(([key, value]) => {
		return value.period == 7;
	});
</script>

<a href="/learning/">Learning</a>
> <a href="/learning/chemistry">Chemistry</a>
> Table
<h2>Period 1</h2>
<div class="atom-grid period-1">
	{#each per1 as [key, value]}
		<Atom {key} {value} />
	{/each}
</div>

<h2>Period 2</h2>
<div class="atom-grid period-2">
	{#each per2 as [key, value]}
		<Atom {key} {value} />
	{/each}
</div>

<h2>Period 3</h2>
<div class="atom-grid period-3">
	{#each per3 as [key, value]}
		<Atom {key} {value} />
	{/each}
</div>

<h2>Period 4</h2>
<div class="atom-grid period-4">
	{#each per4 as [key, value]}
		<Atom {key} {value} />
	{/each}
</div>

<h2>Period 5</h2>
<div class="atom-grid period-5">
	{#each per5 as [key, value]}
		<Atom {key} {value} />
	{/each}
</div>

<h2>Period 6</h2>
<div class="atom-grid period-6">
	{#each per6 as [key, value]}
		<Atom {key} {value} />
	{/each}
</div>

<h2>Period 7</h2>
<div class="atom-grid period-7">
	{#each per7 as [key, value]}
		<Atom {key} {value} />
	{/each}
</div>

<style lang="scss">
	h2 {
		font-size: 2em;
		margin-top: 0;
	}
	.atom-grid {
		display: flex;
		flex-wrap: wrap;
		gap: 2em;
		margin-bottom: 2em;
	}
</style>
