<script>
	import atoms from '$lib/atoms.json';
</script>

<h2>Chemistry</h2>

<ul>
	<li>
		<a href="/chemistry/gases"> Gases </a>
	</li>

	<li>
		<a href="/chemistry/table"> Table </a>
	</li>

	<li>
		<a href="/chemistry/glossary"> Glossary</a>
	</li>
</ul>

<select>
	{#each Object.entries(atoms) as [key, value]}
		<option value={key}>{value.name} – {value.atomicWeight} </option>
	{/each}
</select>
