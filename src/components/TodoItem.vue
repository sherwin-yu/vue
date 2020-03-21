<template>
  <div>
    <div v-for="todo in todos" :key="todo">
      <div class="todo-item">{{todo}}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  data() {
    return {
      todos: ["sleep", "wake up", "eat", "gym"]
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.todo-item {
  padding: 10px 5px;
  background-color: #f6f6f6;
  border-bottom: 1px solid lightgray;
}
</style>
