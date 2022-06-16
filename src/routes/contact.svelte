<script>
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
		margin-top: 0em;
	}

	.form {
		@media screen and (max-width: 24em) {
			width: 98%;
		}

		width: 20em;
		display: grid;
		gap: 0.5em;

		label {
			font-size: 0.8em;
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
