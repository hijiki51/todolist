<template>
  <div>
    <h1>{{ msg }}</h1>
    <todo-list />
  </div>
</template>

<script>
import TodoList from "./todolist.vue";
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  components: {
    TodoList
  }
};
</script>
