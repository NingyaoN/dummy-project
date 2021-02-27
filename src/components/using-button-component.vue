<template>
  <h3>Custom components</h3>
  <div class="w">
    <input
      v-model="color"
      placeholder="Change color (primary | secondary | danger)"
    />
    <input
      v-model="variant"
      placeholder="Change variant (outlined | contained)"
    />
    <input v-model="size" placeholder="Change size (sm | md | lg)" />
  </div>
  <n-button
    style="width: 100%"
    v-bind:size="size"
    v-bind:color="color"
    v-bind:variant="variant"
  >
    MY CUSTOM BUTTON
  </n-button>
</template>

<script>
import Button from './custom-component/button.vue';
export default {
  components: {
    'n-button': Button,
  },

  data() {
    return {
      size: '',
      color: '',
      variant: '',
    };
  },
};
</script>

<style scoped>
input {
  margin-bottom: 30px;
  min-width: 200px;
  height: 30px;
}

.w {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-between;
}
</style>
