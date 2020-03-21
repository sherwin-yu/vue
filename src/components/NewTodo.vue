<template>
  <div>
    <input class="text-input" type="text" />
    <button class="submit" type="submit">Submit</button>
  </div>
</template>

<script>
export default {
  name: "New Todo"
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