<template>
  <h3>List rendering v-for & v-on:keyup.enter</h3>
  <input
    v-on:keyup.enter="reset"
    placeholder="Add Todo"
    v-model="newTodo"
    @change="addTodo"
  />
  <ol>
    <li @click="removeTodo(todo)" v-for="todo in todos" :key="todo.id">
      <span>{{ todo.item }}</span> <span>x</span>
    </li>
  </ol>
</template>
<script>
export default {
  name: 'ListRendering',
  data() {
    return {
      newTodo: '',
      todos: [
        {
          id: 1,
          item: 'Cook',
        },
        {
          id: 2,
          item: 'Spin',
        },
        {
          id: 3,
          item: 'Wash',
        },
        {
          id: 4,
          item: 'Live',
        },
      ],
    };
  },
  methods: {
    reset() {
      this.newTodo = '';
    },
    removeTodo(todo) {
      this.todos = this.todos.filter((t) => t !== todo);
    },
    addTodo() {
      this.todos = [
        { id: this.todos.length + 1, item: this.newTodo },
        ...this.todos,
      ];
    },
  },
};
</script>
<style scoped>
ol {
  list-style-type: none;
  color: black;
}
li {
  margin: 5px;
  background-color: #06d6a0;
  padding: 5px;
  color: white;
  text-align: center;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
}
input {
  margin-top: 30px;
  min-width: 200px;
  height: 30px;
}
</style>
