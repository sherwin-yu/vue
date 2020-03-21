<template>
  <div class="home">
    <Title msg="Todos" />
    <div class="todos">
      <TodoItem />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Title from "@/components/Title.vue";
import TodoItem from "@/components/TodoItem.vue";

export default {
  name: "Home",
  components: {
    Title,
    TodoItem
  }
};
</script>

<style scope>
.todos {
  width: 50%;
  margin: 0 auto;
}
</style>
