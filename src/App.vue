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
    --bg-primary: #0d0237;
    --bg-secondary: #2b2152;
    --text-secondary: #a00710;
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
  .text-secondary {
    color: var(--text-secondary);
  }
</style>
