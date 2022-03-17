<template>
  <div class="todo-footer">
    <input type="checkbox" @change="changeItemsDone($event)" />
    <span>已完成 {{ done }} / 全部 {{ items.length }}</span>
    <el-button type="danger" @click="deleteItems">清除已完成的任务</el-button>
  </div>
</template>

<script>
export default {
    name: 'TodoFooter',
    props: ['items', 'deleteItems'],
    computed: {
        done() {
            let count = 0
            this.items.forEach((item) => {
                if(item.done == true) count++
            })
            return count
        }
    },
    methods: {
        changeItemsDone(e) {
            if(e.target.checked) {
                this.items.forEach((item) => {
                item.done = true
            })}else {
                this.items.forEach((item) => {
                    item.done = false
                })
            }
        },
    }
}
</script>

<style>
.todo-footer {
  display: flex;
  justify-content: space-between;
}
</style>