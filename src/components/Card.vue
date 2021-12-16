<template>
  <div :class="['card', className]">
    <p class="card__title">
      {{ title }}
    </p>
    <p class="card__value">
      {{ value }}
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
  };
</script>
<style scoped>
  .card {
    background-color: var(--bg-primary);
    border-radius: 10px;
    width: 100%;
    height: 100%;
  }
</style>
