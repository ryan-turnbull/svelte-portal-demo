<script>
	import { onMount } from 'svelte'
	import { navigate } from 'svelte-routing'

	import { session } from '../store/user'
	import Card from '../components/wrappers/Card.svelte'

	import { HOME } from '../constants/routes'

	let username = ''
	let password = ''
	let autoLogin = null
	let submitting = false
	$: buttonDisabled = !username || !password

	onMount(() => {
		if ($session) {
			autoLogin = setTimeout(() => {
				navigate(HOME, { replace: false })
			}, 3000)
		}
	})

	function handleSubmit() {
		submitting = true

		setTimeout(() => {
			session.set('ABC-123')
			navigate(HOME, { replace: false })
		}, 3000)
	}

	function cancelLogin() {
		clearTimeout(autoLogin)
		session.set(0)
	}
</script>

<div class="container">
	<Card class="content">
		{#if $session}
			<h3>Wait... i remember that face</h3>
			<button on:click="{cancelLogin}">Cancel auto-login</button>
		{:else}
			<h3>So, who are you?</h3>
			<form on:submit|preventDefault="{handleSubmit}">
				<input bind:value="{username}" placeholder="Username">
				<input type="password" bind:value="{password}" placeholder="Password">
				<button type="submit" disabled="{buttonDisabled || submitting}">
					{#if submitting}
						Pretending to verify...
					{:else}
						Login
					{/if}
				</button>
			</form>
		{/if}
		
	</Card>
</div>

<style>
	.container {
		display: flex;
		min-height: 100vh;
		align-items: center;
		justify-content: center;
	}
	.container :global(.card-svelte) {
		padding: 16px 32px;
	}

	form {
		width: 300px;
		margin: 24px 0;
	}
	form > button, input {
		width: 100%
	}
</style>
