<script>
	export let key = '';
	export let value = {};
</script>

<a href={'/atom/' + key}>
	<div class={'atom ' + 'period-' + value.period}>
		<div>
			<div class="number">
				{value.atomicNumber}
			</div>
			<h2>{value.symbol}</h2>
			<div class="name">
				{value.name}
			</div>
			<div class="atomic-weight">
				{value.atomicWeight}
			</div>
		</div>

		<div class="shells">
			{#each value.shells as shell, i}
				<div class="shell">
					{shell}
				</div>
			{/each}
		</div>
	</div>
</a>

<style lang="scss">
	a {
		color: black;
		text-decoration: none;
	}
	.atom {
		display: inline-flex;
		gap: 2em;
		justify-content: space-between;
		padding: 1em;
		border-radius: 0.5em;
		border: dashed;

		box-sizing: border-box;
		min-width: 10em;
		transition: all 0.2s ease;
		cursor: pointer !important;

		&:hover {
			opacity: 0.72;
		}

		&:active {
			transform: scale(0.95);
		}

		h2 {
			font-size: 4em;
			margin: 0;
		}

		.name {
			margin-bottom: 0.25em;
		}

		.number {
			font-size: 1.5em;
		}

		.atomic-weight {
			font-size: 1.15em;
		}

		.shells {
			font-size: 0.85em;
			text-align: right;
			color: #fff;
		}

		&.period-1 {
			background: mediumaquamarine;
		}

		&.period-2 {
			background: plum;
		}

		&.period-3 {
			background: lightcoral;
		}

		&.period-4 {
			background: paleturquoise;
		}

		&.period-5 {
			background: lightsalmon;
		}

		&.period-6 {
			background: palegoldenrod;
		}

		&.period-7 {
			background: pink;
		}
	}
</style>
