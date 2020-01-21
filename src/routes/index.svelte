<script>
  import {link} from 'svelte-spa-router';
  import { fade } from 'svelte/transition';

  const src = 'images/svelte512.png';

  let curriculumList = [
    {
      id: 1,
      label: 'SvelteでHelloWorld!',
      code: '/helloWorld',
      sample: '',
      completed: false
    },
    {
      id: 2,
      label: '関数を作ってみよう！',
      code: '/function',
      sample: '',
      completed: false
    },
    {
      id: 3,
      label: '変数をリアクティブにしよう！',
      code: '/reActive',
      sample: '',
      completed: false
    },
    {
      id: 4,
      label: 'フォームを作ってみよう！',
      code: '/form',
      sample: '',
      completed: false
    },
    {
      id: 5,
      label: '条件分岐をしてみよう！',
      code: '/if',
      sample: '',
      completed: false
    },
    {
      id: 6,
      label: 'Svelteでリスト表示をしてみよう！',
      code: '/list',
      sample: '',
      completed: false
    },
    {
      id: 7,
      label: 'Svelteでアニメーション！',
      code: '/transition',
      sample: '',
      completed: false
    },
    {
      id: 8,
      label: 'TodoListを作ってみよう！',
      code: '/todo',
      sample: '/todoSample',
      completed: false
    }
  ];

  let bonuses = [
    {
      url: 'https://sapper.svelte.dev/',
      title: 'Sapper',
      color: '#159794',
      description: '(環境構築・SSR・静的化などができるNext.jsやNuxt.jsのようなFW)'
    },
    {
      url: 'https://svelte-native.technology/',
      title: 'Svelte Native',
      color: '#3C5AFD',
      description: '(React Naitiveのようなネイティブモバイルアプリを作ることができるFW)'
    },
    {
      url: 'https://qiita.com/tags/svelte',
      title: 'Qiita',
      color: '#54C500',
      description: '(QiitaのSvelte記事一覧)'
    }
  ]

  let curriculums = JSON.parse(localStorage.getItem("curriculumList") || JSON.stringify(curriculumList));

  function completedSave() {
    localStorage.setItem("curriculumList", JSON.stringify(curriculums));
  }

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

.Congratulations {
  font-family: 'Comic Sans MS', cursive;
	font-size: 2em;
}

.expansion {
  margin-top:30px;
}
</style>

<div id="wrapper">
  
  <h1><img {src} alt="svelte image"  width="50" height="50"/>Svelte ハンズオン</h1>
  <p>
    参考： <a href="https://svelte.dev/docs" target="_blank">公式ドキュメント</a>
  </p>

  <p style="margin-top:30px;">
    終わったらチェックしましょう！　全部クリアすると...
  </p>

  <ul class="curriculum-list">
  {#each curriculums as curriculum}
    <li class="curriculum-list_item">
      <label class="curriculum-list_item-check">
        <input type="checkbox" bind:value={curriculum.id} bind:checked={curriculum.completed} on:change={completedSave}>
        <span class="curriculum-list_item-label">
          {curriculum.id}. {curriculum.label}
        </span>
      </label>
      <span class="curriculum-list_item-link-to-code">
        <a href={curriculum.code} use:link>
          タスク
        </a>
      </span>
      <span class="curriculum-list_item-link-to-ref">
      {#if curriculum.sample}
        <a href={curriculum.sample} use:link>
          サンプル
        </a>
      {/if}
      </span>
    </li>
  {/each}
  </ul>
  {#if curriculums.every((x) => (x.completed === true ))}
    <div class="expansion" transition:fade>
      <span class="Congratulations">Congratulations!</span>
      <p style="margin-top:30px; font-weight:bold;">
        おまけ
      </p>
      {#each bonuses as bonus}
        <p>
          <a href={bonus.url} style="color:{bonus.color}">
            {bonus.title}
          </a>
          {bonus.description}
        </p>
      {/each}
    </div>
  {/if}
</div>
