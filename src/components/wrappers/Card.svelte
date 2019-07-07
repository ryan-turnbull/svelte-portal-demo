<script>
	let className = ''
	export { className as class }
</script>

<style>
	div {
		display: flex;
		border-radius: 4px;
		align-items: center;
		flex-direction: column;
		box-shadow: 0px 5px 15px rgba(0,0,0,0.08)
	}
</style>

<div class="card-svelte">
	<slot></slot>
</div>