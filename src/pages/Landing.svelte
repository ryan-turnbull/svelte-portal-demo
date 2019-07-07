<script>
	import { Link } from 'svelte-routing'
	import { fade } from 'svelte/transition'

	import { LOGIN } from '../constants/routes'
</script>

<style>
	.container {
		display: flex;
		min-height: 100vh;
		align-items: center;
		flex-direction: column;
		justify-content: center;
	}

	.buttons {
		display: flex;
		margin-top: 16px;
	}

	button {
		border: none;
		height: 48px;
		width: 150px;
		margin: 0 8px;
		cursor: pointer;
		border-radius: 4px;
		transition: background-color .2s ease;
	}
	.primary {
		color: #fff;
		background-color: rgb(67, 185, 72);
	}
	.primary:hover {
		background-color: rgb(37, 139, 42);
	}
	.secondary {
		background-color: #fff;
		border: 1px solid #000;
	}
	.secondary:hover {
		background-color: #ddd;
	}
</style>

<div class="container">
	<h1>Welcome</h1>
	<p>Feel free to login, or you can have a nosey</p>
	<section class="buttons">
		<button class="secondary">Have a nosey</button>
		<Link to={LOGIN}>
			<button class="primary">Login</button>
		</Link>
	</section>
</div>
