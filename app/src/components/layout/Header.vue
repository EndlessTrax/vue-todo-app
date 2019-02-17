<template>
  <header class="header">
    <h1>To Do List</h1>
    <small>with Vue.js</small>
  </header>
</template>

<script>
export default {
  name: "Header"
};
</script>

<style scoped lang="scss">
.header {
  background: #292929;
  color: white;
  text-align: center;
  padding: 25px;
}
h1 {
  font-family: "Lucida Sans", "Verdana", sans-serif;
}
</style>