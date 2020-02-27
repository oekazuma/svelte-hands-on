<script>
  import Box from './components/10_Box.svelte';
  let name = 'oe'
  let skills = 'svelte'
</script>

<h1>props</h1>

<Box name={name} skills={skills}/>
<Box/>