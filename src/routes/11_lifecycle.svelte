<script>
	import { onMount } from 'svelte';

	let books = [];

	onMount(async () => {
		const res = await fetch(`https://www.googleapis.com/books/v1/volumes?q=javascript`);
		books = await res.json().then(response => response.items);
	});
</script>

<style>
	.books {
		width: 100%;
		display: grid;
		grid-template-columns: repeat(5, 1fr);
		grid-gap: 8px;
	}

	img {
		width: 95%;
		margin: 0;
	}
</style>

<h1>Book List</h1>

<div class="books">
	{#each books as book}
    <a href={book.volumeInfo.infoLink}>
			<img src={book.volumeInfo.imageLinks.thumbnail} alt={book.volumeInfo.title}>
			<p>{book.volumeInfo.title}</p>
    </a>
	{/each}
</div>