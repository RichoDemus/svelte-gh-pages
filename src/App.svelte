<script>
	let counter = 0;
</script>

<style>
	h1 {
		color: purple;
	}
</style>

<h1>Hello, counter is {counter}!</h1>
<button on:click="{() => counter += 1}">+</button>
<button on:click="{() => counter -= 1}">-</button>
