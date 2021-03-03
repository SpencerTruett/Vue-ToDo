<template>
  <div>
    <h2 :class="{ completed: todo.complete }">{{ todo.name }}</h2>
    <button @click="handleClick">Mark Completed</button>
  </div>
</template>

<script>
export default {
  props: ["todo"],
  methods: {
    handleClick() {
      this.$emit("status-change", this.todo);
    }
  }
};
</script>

<style scoped>
div {
  border: 3px solid tomato;
  margin: 15px;
  padding: 10px;
}
.completed {
  text-decoration: line-through;
  text-decoration-color: tomato;
}
</style>