<template>
  <div>
    <div v-for="todo in todos" :key="todo.name">
      <div class="todo-item">
        <div class="flex-container">
          <div v-bind:class="{'is-completed': todo.isCompleted}">
            <input type="checkbox" v-on:change="handleChange(todo)" />
            {{todo.name}}
          </div>
          <button class="del-button">Delete</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  data() {
    return {
      todos: [
        {
          name: "sleep",
          isCompleted: false
        },
        { name: "wake up", isCompleted: true },
        { name: "eat", isCompleted: false },
        { name: "gym", isCompleted: true }
      ]
    };
  },
  methods: {
    handleChange(todo) {
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
}
.is-completed {
  text-decoration: line-through;
}
</style>
