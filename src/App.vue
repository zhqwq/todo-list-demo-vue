<template>
  <div class="todo-root">
    <h2>待办事项</h2>
    <TodoHeader :addItem="addItem"></TodoHeader>
    <TodoList :items="items" :changeItemDone="changeItemDone"></TodoList>
    <TodoFooter :items="items" :deleteItems="deleteItems"></TodoFooter>
  </div>
</template>

<script>
/* eslint-disable */
import TodoHeader from "./components/TodoHeader";
import TodoList from "./components/TodoList";
import TodoFooter from "./components/TodoFooter";

export default {
  name: "App",
  components: {
    TodoHeader,
    TodoList,
    TodoFooter,
  },
  data() {
    return {
      items: [
        {
          id: "1",
          name: "Leetcode练习",
          done: false,
        },
        {
          id: "2",
          name: "跑500米",
          done: false,
        },
        {
          id: "3",
          name: "按时吃早饭",
          done: true,
        },
      ],
    };
  },
  methods: {
    addItem(name) {
      if(name.trim() == '') {
        alert("输入不能为空")
        return
      }

      let item = {id: Date.now(), name: name, done: false};
      this.items.push(item);
    },
    changeItemDone(id) {
      this.items.some((item) => {
        if(item.id == id) {
          item.done = !item.done
          return true
        }
      })
    },
    deleteItems() {
      this.items = this.items.filter(item => {
        return item.done == false
      })
    }
  }
};
</script>

<style scoped>
.todo-root {
  border: 1px solid #ccc;
  border-radius: 5px;
  padding: 10px;
}
</style>

