<template>
  <Home />
</template>

<script>
  import Home from '@/views/Home.vue';
  export default {
    name: 'App',
    components: {
      Home,
    },
  };
</script>

<style>
  :root {
    --bg-primary: #2b2e4a;
    --bg-secondary: #141626;
    --text-primary: #ce4145;
    --text-secondary: #5f648e;
  }
  * {
    margin: 0;
    box-sizing: border-box;
    font-family: sans-serif;
  }
  body {
    margin: 0;
    padding: 0;
  }
  .text-primary {
    color: var(--text-primary);
  }
  .text-secondary {
    color: var(--text-secondary);
  }
</style>
