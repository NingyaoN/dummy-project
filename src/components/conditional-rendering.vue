<template>
  <h3>
    Conditional rendering v-if
  </h3>
  <div @click="setShow" class="item">
    <p>{{ changeTitle }}</p>
    <p v-if="show">Bekaaboooo....</p>
  </div>
</template>
<script>
export default {
  name: 'ConditionalRendering',
  data() {
    return {
      show: false,
    };
  },
  computed: {
    changeTitle() {
      return this.show ? 'Click to Show' : 'Click to hide';
    },
  },
  methods: {
    setShow() {
      this.show = !this.show;
    },
  },
};
</script>
<style scoped>
.item {
  width: 200px;
  height: 50px;
  background-color: red;
}
p {
  color: white;
}
</style>
