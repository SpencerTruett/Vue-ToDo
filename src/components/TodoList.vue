<template>
  <div>
    <h3>Here is the To Do List</h3>
  </div>
</template>

<script>
import { todoItems } from "../data";

export default {
  data() {
    return {
      todos: [...todoItems]
    };
  }
};
</script>

<style></style>
