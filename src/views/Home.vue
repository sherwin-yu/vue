<template>
  <div class="home">
    <Title msg="Todos!" />
    <div class="todos">
      <NewTodo v-on:add-todo="addTodo" />
      <Todos v-bind:todos="todos" v-on:del-todo="handleDelete" />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Title from "@/components/Title.vue";
import NewTodo from "@/components/NewTodo.vue";
import Todos from "@/components/Todos.vue";

export default {
  name: "Home",
  components: {
    Title,
    NewTodo,
    Todos,
  },
  data() {
    return {
      todos: [
        { id: 1, name: "sleep", isCompleted: false },
        { id: 2, name: "wake up", isCompleted: true },
        { id: 3, name: "eat", isCompleted: false },
        { id: 4, name: "gym", isCompleted: true },
      ],
    };
  },
  methods: {
    handleDelete(deletedTodo) {
      this.todos = this.todos.filter((todo) => todo.id != deletedTodo);
    },
    addTodo(newTodo) {
      this.todos = [...this.todos, newTodo];
    },
  },
};
</script>

<style scope>
.todos {
  width: 50%;
  margin: 0 auto;
}
</style>
