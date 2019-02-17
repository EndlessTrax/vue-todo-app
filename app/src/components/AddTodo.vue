<template>
  <div>
    <form @submit="addTodo">
      <input type="text" v-model="title" name="title" placeholder="Add Todo...">
      <input type="submit" value="Submit" class="submit-btn">
    </form>
  </div>
</template>

<script>
export default {
  name: "AddTodo",
  data() {
    return {
      title: ""
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      const newTodo = {
        title: this.title,
        completed: false
      };
      // Send up to parent
      this.$emit("add-todo", newTodo);
      // CLear form
      this.title = "";
    }
  }
};
</script>

<style scoped lang="scss">
form {
  display: flex;
}
input[type="text"] {
  flex: 10;
  padding: 10px;
}
input[type="submit"] {
  flex: 2;
  padding: 10px;
}
.submit-btn {
  background: greenyellow;
  border-radius: 5px;
  font-family: Arial, Helvetica, sans-serif;
  text-transform: uppercase;
}
.submit-btn:hover {
    background: green;
}
</style>