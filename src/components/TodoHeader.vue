<template>
  <el-input v-model="input" placeholder="请输入待办事项，按回车键确认" @keyup.enter="addItem(input, $event)"/>
</template>

<script>
export default {
    name: 'TodoHeader',
    data(){
      return {
        input: ''
      }
    },
    props: ['addItem']
}
</script>

<style>

</style>