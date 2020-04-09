<template>
  <div>
    <div class="todo-item">
      <div class="flex-container">
        <div :class="{'is-completed': todo.isCompleted}">
          <input type="checkbox" v-model="todo.isCompleted" @change="handleChange(todo)" />
          {{todo.name}}
        </div>
        <button class="del-button" @click="$emit('del-todo', todo.id)">Delete</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    handleChange(selectedTodo) {
      const todo = this.todos.filter(todo => todo.id === selectedTodo.id);
      todo.isCompleted = !todo.isCompleted;
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
