<template>
  <button class="btn">
    <slot></slot>
  </button>
</template>

<script>

export default {
  name: 'my-button'
}

</script>

<style scoped>

.btn {
  background: none;
  padding: 12px;
  color: #2a2828;
  font-weight: 600;
  transition: 0.2s;
}

</style>