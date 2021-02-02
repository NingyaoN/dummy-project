<template>
  <h3>Class And Style Binding</h3>
  <p v-if="!isChar" :class="{ error: !isChar }">Please enter UPPERCASE only</p>
  <input
    v-model="text"
    @change="checkChar()"
    placeholder="Accept UPPERCASE only"
  />
</template>

<script>
export default {
  name: 'ClassAndStyleBinding',
  data() {
    return {
      isChar: true,
      text: '',
      regx: /[A-Z]/,
    };
  },

  methods: {
    checkChar() {
      console.log('chiecking');
      this.isChar = this.regx.test(this.text);
    },
  },
};
</script>
<style scoped>
input {
  margin-top: 30px;
  min-width: 200px;
  height: 30px;
}
.error {
  color: red;
}
</style>
