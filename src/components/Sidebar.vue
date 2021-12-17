<template>
  <div class="sidebar">
    <h2 class="sidebar__header">
      <a href="/">pi-<span class="text-primary">info</span></a>
    </h2>
  </div>
</template>
<script>
  export default {
    name: 'Sidebar',
  };
</script>

<style scoped>
  .sidebar {
    height: 100vh;
    width: 15%;
    background-color: var(--bg-primary);
    color: #fff;
  }
  .sidebar__header {
    text-align: center;
    margin-top: 1rem;
    text-decoration: none;
    font-weight: normal;
  }
  .sidebar__header a,
  .sidebar__header a:visited {
    text-decoration: none;
    color: #fff;
  }
</style>
