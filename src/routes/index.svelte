<script>
import {link} from 'svelte-spa-router';
import { onMount } from 'svelte';

const keyCheckedCurriculum = 'CHECKED_CURRICULUM_LIST';
const src = 'images/svelte512.png';

let curriculumList = [
  {
    id: 1,
    label: 'SvelteでHelloWorld!',
    code: '/helloWorld',
    reference: '',
    completed: false
  },
  {
    id: 2,
    label: '関数を作ってみよう！',
    code: '/function',
    reference: '',
    completed: false
  },
  {
    id: 3,
    label: '変数をリアクティブにしよう！',
    code: '/reActive',
    reference: '',
    completed: false
  },
  {
    id: 4,
    label: 'フォームを作ってみよう！',
    code: '/form',
    reference: '',
    completed: false
  },
  {
    id: 5,
    label: '条件分岐をしてみよう！',
    code: '/if',
    reference: '',
    completed: false
  },
  {
    id: 6,
    label: 'Svelteでリスト表示をしてみよう！',
    code: '/list',
    reference: '',
    completed: false
  },
  {
    id: 7,
    label: 'Svelteでアニメーション！',
    code: '/transition',
    reference: '',
    completed: false
  }
];




</script>

<style>

#wrapper {
  width: max-content;
  margin: auto;
}

h1 {
  color: #2c3e50;
  font-weight: 600;
}

a {
  color: #ff3e00;
  font-weight: 600;
  text-decoration: none;
}

.curriculum-list {
  display: grid;
  grid-template-columns: repeat(3, max-content);
  grid-row-gap: 20px;
  margin: 30px auto 0;
  padding: 0;
  list-style: none;
}

.curriculum-list_item {
  display: contents;
}

.curriculum-list_item-check {
  display: flex;
  align-items: center;
  cursor: pointer;
}

.curriculum-list_item-check [type="checkbox"] {
  margin-right: .7em;
}

.curriculum-list_item-label {
  font-weight: 600;
}

.curriculum-list_item-link-to-code,
.curriculum-list_item-link-to-ref {
  padding-left: .8em;
  text-align: left;
  counter-reset: ref;
}

.curriculum-list_item-link-to-code a,
.curriculum-list_item-link-to-ref a {
  display: inline-flex;
  align-items: center;
  margin-left: .5em;
}
</style>

<div id="wrapper">
  
  <h1><img {src} alt="svelte image"  width="50" height="50"/>Svelte ハンズオン</h1>
  <p>
    今回作るもの： <a href="/todo" use:link>簡易 TODO リスト</a>
  </p>

  <p style="margin-top:30px;">
    参加した、または実施した内容にチェックしましょう！
  </p>

  <ul class="curriculum-list">
  {#each curriculumList as curriculum}
    <li class="curriculum-list_item">
      <label class="curriculum-list_item-check">
        <input type="checkbox" bind:value={curriculum.id} bind:checked={curriculum.completed}>
        <span class="curriculum-list_item-label">
          {curriculum.id}. {curriculum.label}
        </span>
      </label>
      <span class="curriculum-list_item-link-to-code">
        <a href={curriculum.code} use:link>
          作るもの
        </a>
      </span>
      <span class="curriculum-list_item-link-to-ref">
        <a href={curriculum.reference} target="_blank">
          参考
        </a>
      </span>
    </li>
  {/each}
  </ul>
</div>
