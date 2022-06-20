<script lang="ts">
	import projects from '$lib/projects.json';
</script>

<svelte:head>
	<title>Projects</title>
</svelte:head>

<h1>Projects</h1>

<div class="projects">
	{#each projects as project}
		<a href={project.url} target="_blank" class="project">
			<img src={project.image} />

			<div class="info">
				<h2>{project.title}</h2>
				<p>{project.description}</p>
			</div>
		</a>
	{/each}
</div>

<style lang="scss">
	h1 {
		font-size: 2rem;
		margin-bottom: 2rem;
	}

	.projects {
		display: flex;
		align-items: center;
		margin-bottom: 1em;
		gap: 1rem;
		flex-wrap: wrap;
		max-width: 50rem;
		justify-content: center;

		.project {
			color: black;
			transition: all 0.2s ease;
			word-wrap: break-word;
			width: 20rem;
			border: 3px dashed black;
			border-radius: 0.75rem;
			overflow: hidden;
			box-sizing: border-box;
			height: 100%;

			&:active {
				transform: scale(0.98);
			}

			h2 {
				font-size: 1.5rem;
				margin-bottom: 0rem;
			}

			img {
				width: 100%;
				height: 12rem;
				object-fit: cover;
				border-bottom: 3px dashed black;
			}

			.info {
				padding: 0.5rem 1rem;
			}
		}
	}
</style>
