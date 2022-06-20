<script>
	import GithubFill from 'svelte-remixicon/lib/icons/GithubFill.svelte';
	import MailFill from 'svelte-remixicon/lib/icons/MailFill.svelte';

	import TwitterFill from 'svelte-remixicon/lib/icons/TwitterFill.svelte';
	import LinkedinFill from 'svelte-remixicon/lib/icons/LinkedinFill.svelte';
	import CalendarFill from 'svelte-remixicon/lib/icons/CalendarFill.svelte';
	import FileList2Fill from 'svelte-remixicon/lib/icons/FileList2Fill.svelte';

	const contactGrid = [
		{
			title: 'Github',
			link: 'https://github.com/samullman',
			icon: GithubFill
		},

		{
			title: 'Email',
			link: 'mailto:samullman@gmail.com',
			icon: MailFill
		},

		{
			title: 'Twitter',
			link: 'https://twitter.com/samullman',
			icon: TwitterFill
		},

		{
			title: 'LinkedIn',
			link: 'https://linkedin.com/in/samullman',
			icon: LinkedinFill
		},

		{
			title: 'Calendly',
			link: 'https://calendly.com/samullman',
			icon: CalendarFill
		},

		{
			title: 'Resume',
			link: 'https://drive.google.com/file/d/1AX2jec9LUVzymzU0lWuLt9AWP_DFBw5E/view?usp=sharing',
			icon: FileList2Fill
		}
	];

	let name = '';
	let email = '';
	let budget = '';
	let message = '';
	let role = '';
	let organization = '';

	async function formSubmit(event) {
		event.preventDefault();
		var status = document.getElementById('form-status');
		var data = new FormData(event.target);

		fetch(event.target.action, {
			method: 'POST',
			body: data,
			headers: {
				Accept: 'application/json'
			}
		})
			.then((response) => {
				name = '';
				email = '';
				// budget = '';
				message = '';
				organization = '';
				role = '';
				status.innerHTML = 'Thanks for your submission!';
			})
			.catch((error) => {
				status.innerHTML = 'Oops! There was a problem submitting your form';
			});
	}
</script>

<svelte:head>
	<title>Contact</title>
</svelte:head>

<h1>Contact</h1>

<div class="contact-items">
	{#each contactGrid as contact}
		<a href={contact.link} target="_blank">
			<div class="contact">
				<div class="contact-icon">
					<svelte:component this={contact.icon} />
				</div>
				<h4 class="contact-title">
					{contact.title}
				</h4>
			</div>
		</a>
	{/each}
</div>

<form action="https://formspree.io/f/mjvlkrdq" method="post" on:submit={formSubmit} class="form">
	<div>
		<label for="name" aria-required="true">Name</label>
		<div>
			<input type="text" name="name" required bind:value={name} />
		</div>
	</div>

	<div>
		<label for="email">Email</label>
		<div>
			<input type="email" name="email" required bind:value={email} />
		</div>
	</div>

	<div>
		<label for="role">Role</label>
		<div>
			<input type="text" name="role" bind:value={role} />
		</div>
	</div>

	<div>
		<label for="role">Organization</label>
		<div>
			<input type="text" name="role" bind:value={organization} />
		</div>
	</div>

	<!-- <div>
					<label for="budget">Budget</label>
					<div>
						<select class="form-select rounded" name="budget" bind:value={budget}>
							<option />
							<option>$0 - $4,999</option>
							<option>$5000 - $9,999</option>
							<option>$10,000 - $19,999</option>
							<option>$20,000 - $44,999</option>
							<option>$45,000+</option>
						</select>
					</div>
				</div>
			</div> -->

	<div>
		<label for="message">Message</label>
		<div>
			<textarea name="message" rows="3" bind:value={message} />
		</div>
	</div>

	<div>
		<button type="submit" class="btn btn-primary font-normal"> Submit </button>
	</div>
</form>

<div id="form-status" />

<style lang="scss">
	h1 {
		font-size: 2rem;
		margin-top: 0em;
		margin-bottom: 2rem;
	}

	.contact-items {
		max-width: 32rem;
		display: flex;
		align-items: center;
		margin-bottom: 1em;
		gap: 1rem;
		flex-wrap: wrap;
		justify-content: center;

		.contact {
			padding: 1.5rem;
			color: black;
			border: 3px dashed black;
			border-radius: 0.75rem;
			text-align: center;
			transition: all 0.2s ease;

			&:active {
				transform: scale(0.98);
			}

			.contact-icon {
				font-size: 3rem;
			}

			.contact-title {
				font-size: 1.2rem;
				margin: 0;
			}
		}
	}

	.form {
		font-size: 1rem;
		@media screen and (max-width: 24em) {
			width: 98%;
		}

		width: 20em;
		display: grid;
		display: none;

		gap: 0.5em;

		label {
			font-weight: bold;
			display: block;
			margin-bottom: 0.25em;
		}

		input,
		textarea {
			width: calc(100% - 0.5em);
		}
	}
</style>
