<template>
  <div :class="['card', className]">
    <p class="card__title text-secondary">
      {{ title }}
    </p>
    <p class="card__value">
      {{ value }}<span class="card__unit text-primary">{{ unit }}</span>
    </p>
  </div>
</template>
<script>
  export default {
    name: 'Card',
    props: {
      title: String,
      value: null,
      className: String,
    },
    data() {
      return {
        unit: '',
      };
    },
    mounted() {
      if (this.$props.title.includes('temp')) this.unit = '°C';
      if (this.$props.title.includes('usage')) this.unit = '%';
      if (this.$props.title.includes('memory')) this.unit = 'GB';
    },
  };
</script>
<style scoped>
  .card {
    background-color: var(--bg-primary);
    border-radius: 10px;
    width: 100%;
    height: 100%;
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .card__title {
    position: absolute;
    top: 0.7rem;
    left: 0.7rem;
    font-size: 1.2rem;
  }
  .card__value {
    font-size: 3rem;
    font-weight: bold;
    color: #fff;
  }
</style>
