<script>
	import { count } from './stores.js';
	let counter;

	const unsubscribe = count.subscribe(value => {
		counter = value;
	});
</script>

<style>
	h1 {
		color: purple;
	}
</style>

<h1>Hello, counter is {counter}!</h1>
<button on:click="{() => count.update(n => n + 1)}">+</button>
<button on:click="{() => count.update(n => n - 1)}">-</button>
