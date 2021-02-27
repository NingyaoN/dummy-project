<template>
  <h3>Select from handling</h3>
  <p><u>CHECKBOX</u></p>
  <p>ITEMS:: {{ items }}</p>
  <div class="items">
    <label>Apple</label>
    <input type="checkbox" value="apple" v-model="items" />
    <label>mango</label>
    <input type="checkbox" value="mango" v-model="items" />
    <label>berry</label>
    <input type="checkbox" value="berry" v-model="items" />
    <label>orange</label>
    <input type="checkbox" value="orange" v-model="items" />
  </div>
  <p><u>RADIO BUTTON</u></p>
  <p v-if="gender">You have selected:: {{ gender }}</p>
  <div class="items">
    <label for="female">
      Female
    </label>
    <input type="radio" id="female" value="female" v-model="gender" />

    <label for="male">
      Male
    </label>
    <input type="radio" id="male" value="male" v-model="gender" />
  </div>

  <p><u>SINGLEA SELECT</u></p>
  <div class="items">
    <select v-model="selected">
      <option disabled value="">Please select one</option>
      <option>A</option>
      <option>B</option>
      <option>C</option>
    </select>
    <span>Selected: {{ selected }}</span>
  </div>

  <p><u>SELECT MULTIPLE</u></p>
  <div class="items">
    <select v-model="multiple" multiple>
      <option>A</option>
      <option>B</option>
      <option>C</option>
    </select>
    <br />
    <span>Multiple Selected: {{ multiple }}</span>
  </div>
</template>
<script>
export default {
  name: 'SelectFormHandling',
  data() {
    return {
      selected: '',
      multiple: [],
      items: [],
      gender: '',
    };
  },
};
</script>
<style scoped>
.items {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
</style>
