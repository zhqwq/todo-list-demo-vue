<template>
  <ul>
    <TodoListItem v-for="item in items" :key="item.id" :item="item" :changeItemDone="changeItemDone"></TodoListItem>
  </ul>
</template>

<script>
import TodoListItem from "./TodoListItem";

export default {
  name: "TodoList",
  components: {
    TodoListItem,
  },
  props: ['items', 'changeItemDone']
};
</script>

<style scoped>
ul {
  padding: 0;
}
li {
  list-style-type: none;
}
</style>