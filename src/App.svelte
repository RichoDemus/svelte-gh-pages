<script>
	import { count } from './stores.js';
	let counter;

	const unsubscribe = count.subscribe(value => {
		counter = value;
	});

	let key;
	let keyCode;
	function handleKeydown(event) {
		key = event.key;
		keyCode = event.keyCode;

		if(key === "+") {
			increment();
		} else if (key === "-") {
			decrement();
		}
	}

	function increment() {
		count.update(n => n + 1)
	}

	function decrement() {
		count.update(n => n - 1)
	}
</script>

<style>
	h1 {
		color: purple;
	}
</style>

<svelte:window on:keydown={handleKeydown}/>

<h1>Hello, counter is {counter}!</h1>
<button on:click="{() => increment()}">+</button>
<button on:click="{() => decrement()}">-</button>
<p>key: {key}, key code: {keyCode}</p>
