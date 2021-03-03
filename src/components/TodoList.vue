<template>
  <div>
    <h3>ToDo List</h3>
    <h4>{{ itemsRemaining }}</h4>
    <div v-for="item in todos" :key="item.id">
      <todo-item :todo="item" @status-change="handleStatusChange" />
    </div>
  </div>
</template>

<script>
import { todoItems } from "../data";
import TodoItem from "./TodoItem.vue";

export default {
  components: { TodoItem },
  data() {
    return {
      todos: [...todoItems]
    };
  },
  methods: {
    handleStatusChange(item) {
      item.complete = !item.complete;
      console.log(item);
    }
  },
  computed: {
    itemsRemaining() {
      const remaining = this.todos.filter(t => !t.complete).length;
      if (remaining === 1) {
        return "There is 1 item left to do today";
      }
      if (remaining === 0) {
        return "There are no item left to do today!";
      }
      return `There are ${remaining} items left to do today`;
    }
  }
};
</script>

<style></style>
