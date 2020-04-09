<template>
  <div>
    <div v-for="todo in todos" :key="todo.id">
      <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)" />
    </div>
  </div>
</template>

<script>
import TodoItem from "./TodoItem.vue";

export default {
  name: "Todos",
  components: {
    TodoItem
  },
  props: ["todos"],
  methods: {
    handleChange(selectedTodo) {
      const todo = this.todos.filter(todo => todo.id === selectedTodo.id);
      todo.isCompleted = !todo.isCompleted;
    },
    handleDelete(deletedTodo) {
      this.todos = this.todos.filter(todo => todo.id != deletedTodo);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.flex-container {
  display: flex;
  justify-content: space-between;
}
.todo-item {
  padding: 10px 15px;
  background-color: #f6f6f6;
  border-bottom: 1px solid lightgray;
}
.del-button {
  background-color: red;
  color: white;
  border: 1px solid transparent;
  cursor: pointer;
}
.is-completed {
  text-decoration: line-through;
}
</style>
