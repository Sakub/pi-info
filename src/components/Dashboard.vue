<template>
  <div class="dashboard">
    <Card title="CPU temp" :value="cpuTemp" class="cpuTemp" />
    <Card title="RAM usage" :value="gpuTemp" class="ramUsage" />
    <Card title="CPU chart" class="cpuChart" />
    <Card title="Available memory" class="memory" />
    <Card title="CPU usage" class="cpuUsage" />
    <Card title="Storage" class="storage" />
  </div>
</template>

<script>
  const API_URL = 'http://localhost:3000';
  import Card from '@/components/Card.vue';
  export default {
    name: 'Dashboard',
    components: {
      Card,
    },
    data() {
      return {
        cpuTemp: 0,
        gpuTemp: 0,
      };
    },
    mounted() {
      fetch(API_URL)
        .then(res => res.json())
        .then(data => {
          this.cpuTemp = data.cpuTemp;
          this.gpuTemp = data.gpuTemp;
        });
    },
  };
</script>
<style scoped>
  .dashboard {
    width: 85%;
    padding: 50px;
    background-color: var(--bg-secondary);
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-template-rows: repeat(3, 1fr);
    gap: 2rem;
    align-items: center;
    justify-content: center;
    grid-template-areas:
      'cpuTemp ramUsage cpuChart cpuChart'
      'memory cpuUsage cpuChart cpuChart'
      'storage storage storage storage';
  }

  .cpuTemp {
    grid-area: cpuTemp;
  }
  .ramUsage {
    grid-area: ramUsage;
  }
  .cpuChart {
    grid-area: cpuChart;
  }
  .memory {
    grid-area: memory;
  }
  .cpuUsage {
    grid-area: cpuUsage;
  }
  .storage {
    grid-area: storage;
  }
</style>
