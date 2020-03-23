<template>
  <div>
    <div v-for="todo in todos" :key="todo">
      <div class="todo-item">
        <div class="flex-container">
          <div>{{todo}}</div>
          <button>Delete</button>
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
      todos: ["sleep", "wake up", "eat", "gym"]
    };
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
</style>
