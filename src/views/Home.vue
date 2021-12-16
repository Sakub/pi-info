<template>
  <div class="wrapper">
    <Sidebar />
    <Dashboard />
  </div>
</template>
<script>
  import Dashboard from '@/components/Dashboard.vue';
  import Sidebar from '@/components/Sidebar.vue';
  export default {
    name: 'Home',
    components: {
      Dashboard,
      Sidebar,
    },
  };
</script>
<style scoped>
  .wrapper {
    display: flex;
    width: 100vw;
  }
</style>
