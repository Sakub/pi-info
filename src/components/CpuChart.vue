<template>
  <div class="chartWrapper">
    <canvas id="cpu-chart"></canvas>
  </div>
</template>
<script>
  import Chart from 'chart.js/auto';
  const config = {
    type: 'line',
    data: {
      labels: [],
      datasets: [
        {
          data: [],
          backgroundColor: '#ce4145',
          borderColor: '#ce4145',
        },
      ],
    },
    options: {
      plugins: {
        legend: {
          display: false,
        },
      },
    },
  };

  const UPDATE_INTERVAL = 6000;

  export default {
    name: 'CpuChart',
    props: {
      tempList: Array,
    },
    mounted() {
      const ctx = document.querySelector('#cpu-chart');
      const chart = new Chart(ctx, config);
      setInterval(() => {
        config.data.datasets[0].data.push(this.$props.tempList.at(-1));
        config.data.labels.push(`${config.data.labels.length + 1}`);
        chart.update();
      }, UPDATE_INTERVAL);
    },
  };
</script>
<style scoped>
  .chartWrapper {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 95%;
  }
</style>
