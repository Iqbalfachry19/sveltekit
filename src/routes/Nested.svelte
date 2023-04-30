<script lang="ts">
	export let answer: number;
	let string = 'this string contains some <strong>HTML!</strong>';
	let count = 0;
	let numbers = [1, 2, 3, 4];

	$: doubled = count * 2;

	$: if (count >= 10) {
		alert('count is dangerously high!');
		count = 0;
	}
	function increment() {
		count += 1;
	}
	function addNumber() {
		numbers.push(numbers.length + 1);
		numbers = numbers;
	}
	$: sum = numbers.reduce((t, n) => t + n, 0);
</script>

<p>{@html string}</p>
<button on:click={increment}>Clicked {count} {count === 1 ? 'time' : 'times'}</button>
<p>{count} doubled is {doubled}</p>
<p>{numbers.join('+')}= {sum}</p>
<button on:click={addNumber}>Add a number</button>
<p>The answer is {answer}</p>
