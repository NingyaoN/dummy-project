<template>
  <div class="error">
    <slot></slot>
  </div>
</template>
<script>
export default {
  name: 'ErrorComponent',
};
</script>
<style scoped>
.error {
  padding: 10px;
  background-color: red;
  color: white;
}
</style>
