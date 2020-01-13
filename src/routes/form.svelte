<script>
	let name = 'world';
</script>

<h1>フォームに入力された値をリアルタイムに表示できるようにバインディングしよう</h1>

<input bind:value={name}>

<h1>Hello {name}!</h1>