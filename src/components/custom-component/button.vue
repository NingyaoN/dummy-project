<template>
  <button
    class="Button"
    v-bind:class="{ [size]: size, [color]: color, [variant]: variant }"
  >
    <slot>Button</slot>
  </button>
</template>
<script>
export default {
  props: {
    size: String,
    color: String,
    variant: String,
    onClick: {
      type: Function,
      required: true,
    },
  },
};
</script>

<style scoped>
button {
  border-radius: 4px;
}
button.outlined {
  border: 1px solid red;
  background-color: transparent;
}

button.lg {
  font-size: 24px;
}

button.sm {
  font-size: 18px;
}

button.contained.primary {
  background-color: blue;
  color: white;
}

button.contained.danger {
  background-color: red;
  color: white;
}
</style>
