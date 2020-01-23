<script>
  import { fade } from 'svelte/transition';
  let visible = true;
</script>

<h1>チェックボックスをクリックすると文字がフェードイン・フェードアウトするようにしよう！</h1>
<label>
	<input type="checkbox" bind:checked={visible}>
	visible
</label>

{#if visible}
	<p>
		フェードインとフェードアウトするよ
	</p>
{/if}