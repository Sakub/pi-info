<template>
  <div class="dashboard">
    <Card title="CPU temp" :value="cpuTemp" class="cpuTemp" />
    <Card title="CPU usage" :value="cpuUsage" class="cpuUsage" />
    <Card title="CPU chart" :tempList="tempList" class="cpuChart" />
    <Card title="Available memory" :value="memoryAvailable" class="memory" />
    <Card title="Lorem" :value="cpuUsage" class="lorem" />
    <Card title="Storage" class="storage" />
  </div>
</template>

<script>
  const API_URL = 'http://localhost:3000';
  const API_CALL_INTERVAL = 5000;
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
        cpuUsage: 0,
        memoryAvailable: 0,
        tempList: [],
      };
    },
    methods: {
      fetchApi() {
        fetch(API_URL)
          .then(res => res.json())
          .then(data => {
            this.cpuTemp = data.cpuTemp;
            this.gpuTemp = data.gpuTemp;
            this.cpuUsage = data.cpuUsage;
            this.memoryAvailable = data.memoryAvailable;
            this.tempList.push(data.cpuTemp);
          });
      },
    },
    mounted() {
      setInterval(this.fetchApi, API_CALL_INTERVAL);
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
      'cpuTemp cpuUsage cpuChart cpuChart'
      'memory lorem cpuChart cpuChart'
      'storage storage storage storage';
  }

  .cpuTemp {
    grid-area: cpuTemp;
  }
  .lorem {
    grid-area: lorem;
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
