<template>
  <li>
    <input type="checkbox" :checked="item.done" @change="changeItemDone(item.id)"/>
    <span>{{item.name}}</span>
  </li>
</template>

<script>
export default {
    name: 'TodoListItem',
    props: ['item', 'changeItemDone'],
};
</script>

<style scoped>
    li {
        padding-bottom: 10px;
    }
</style>