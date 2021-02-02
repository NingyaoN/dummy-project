<template>
  <h3>
    Computed Properties & Watch
  </h3>
  <p>Total Salary :: {{ getTotalSalary }}</p>
  <select name="salary" v-model="selectedEmployee" id="">
    <option>Select Employee</option>
    <option :value="emp.name" v-for="emp in employees" :key="emp.salary">{{
      emp.name
    }}</option>
  </select>
  <br />
  <input placeholder="Enter new salary" v-model="newSalary" />
</template>

<script>
export default {
  name: 'ComputedProperties',
  data() {
    return {
      newSalary: 0,
      selectedEmployee: '',
      employees: [
        {
          name: 'john doe',
          salary: 200,
        },
        {
          name: 'Lucy Hill',
          salary: 320,
        },
        {
          name: 'Mark Twain',
          salary: 210,
        },
      ],
    };
  },

  watch: {
    newSalary(newValue) {
      console.log('selected', this.selectedEmployee);
      this.employees = this.employees.map((emp) => {
        if (this.selectedEmployee === emp.name) {
          emp.salary = newValue;
          return emp;
        }

        return emp;
      });
    },
  },
  computed: {
    getTotalSalary() {
      return this.employees.reduce(
        (acc, next) => acc + parseInt(next.salary),
        0
      );
    },
  },
};
</script>

<style scoped>
select {
  min-width: 200px;
  height: 30px;
  border-radius: 4px;
  font-size: 20px;
}

input {
  margin-top: 30px;
  min-width: 200px;
  height: 30px;
}
</style>
