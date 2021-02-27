<template>
  <h3>Passing Props</h3>
  <h5>{{ header }}</h5>
  <p>
    For passing dynamic props bind with :propName (refer custom components
    section ) &larr;
  </p>
</template>
<script>
export default {
  name: 'ComponentInDepth',
  props: {
    header: String,
  },
};
</script>
