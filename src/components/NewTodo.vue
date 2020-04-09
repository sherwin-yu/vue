<template>
  <form @submit="addTodo">
    <input
      class="text-input"
      type="text"
      v-model="name"
      name="name"
      placeholder="Add Todo..."
      required
    />
    <button class="submit" type="submit" value="Submit">Submit</button>
  </form>
</template>

<script>
import { v4 as uuidv4 } from "uuid";

export default {
  name: "NewTodo",
  data() {
    return {
      name: "",
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      const newTodo = {
        id: uuidv4(),
        name: this.name,
        isCompleted: false,
      };
      this.name = "";
      this.$emit("add-todo", newTodo);
    },
  },
};
</script>

<style scoped>
.text-input {
  padding: 10px 15px;
}
.submit {
  padding: 10px 15px;
  background-color: #42b983;
  border: 1px solid transparent;
  color: white;
}
</style>
