<script>
	import atoms from '$lib/atoms.json';
</script>

<a href="/learning/">Learning</a>
> Chemistry

<h2>Chemistry</h2>

<ul>
	<li>
		<a href="/learning/chemistry/gases"> Gases </a>
	</li>

	<li>
		<a href="/learning/chemistry/table"> Table </a>
	</li>

	<li>
		<a href="/learning/chemistry/glossary"> Glossary</a>
	</li>
</ul>

<select>
	{#each Object.entries(atoms) as [key, value]}
		<option value={key}>{value.name} – {value.atomicWeight} </option>
	{/each}
</select>
