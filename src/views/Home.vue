<template>
  <div class="home">
    <HelloWorld msg="Todos" />
    <TodoItem />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import TodoItem from "@/components/TodoItem.vue";

export default {
  name: "Home",
  components: {
    HelloWorld,
    TodoItem
  }
};
</script>
