<script>
	let count = 0;
	let doubled = count * 2;

	function handleClick() {
		count += 1;
	}
</script>

<h1>変数 doubledを再計算できるようにしてリアクティブにしよう！</h1>
<button on:click={handleClick}>
	Clicked {count} {count === 1 ? 'time' : 'times'}
</button>

<p>{count} doubled is {doubled}</p>