<script>
import Router from 'svelte-spa-router'
import Index from './routes/index.svelte'
import HelloWorld from './routes/01_helloWorld.svelte'
import Function from './routes/02_function.svelte'
import ReActive from './routes/03_reActive.svelte'
import Form from './routes/04_form.svelte'
import If from './routes/05_if.svelte'
import List from './routes/06_list.svelte'
import Transition from './routes/07_transition.svelte'
import Todo from './routes/08_todo.svelte'
import TodoSample from './routes/sample/todo.svelte'
import Component from './routes/09_component.svelte'
import Props from './routes/10_props.svelte'
import Lifecycle from './routes/11_lifecycle.svelte'
import Store from './routes/12_store.svelte'
import BookList from './routes/13_bookList.svelte'


const routes = {
    '/': Index,
    '/helloWorld/': HelloWorld,
    '/function': Function,
    '/reActive': ReActive,
    '/form': Form,
    '/if': If,
    '/list': List,
    '/transition': Transition,
    '/todo': Todo,
    '/todoSample': TodoSample,
    '/component': Component,
    '/props': Props,
    '/lifecycle': Lifecycle,
    '/store': Store,
    '/booklist': BookList
}
</script>

<style>
body {
  margin: 0;
  padding: 0 15px 15px;
  font-family: "Source Sans Pro", "Helvetica Neue", Arial, sans-serif;
  font-size: 16px;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #34495e;
  text-align: center;
  }
</style>

<body>
    <Router {routes}/>
</body>