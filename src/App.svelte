<script>
import Router from 'svelte-spa-router'
import Index from './routes/index.svelte'
import HelloWorld from './routes/helloWorld.svelte'
import Function from './routes/function.svelte'
import ReActive from './routes/reActive.svelte'
import Form from './routes/form.svelte'
import If from './routes/if.svelte'
import List from './routes/list.svelte'
import Transition from './routes/transition.svelte'
import Todo from './routes/todo.svelte'


const routes = {
    '/': Index,
    '/helloWorld/': HelloWorld,
    '/function': Function,
    '/reActive': ReActive,
    '/form': Form,
    '/if': If,
    '/list': List,
    '/transition': Transition,
    '/todo': Todo
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