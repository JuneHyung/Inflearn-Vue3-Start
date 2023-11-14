<template>
  <ul>
    <li v-for="(item, idx) in todoItems" :key="idx">
      <span>{{ item }}</span>
      <buton>삭제</buton>
    </li>
  </ul>  
</template>

<script>
  export default {
    props: ['todoItems', 'userId'],
    setup(props, context){
      function removeTodo(item, index){
        context.emit('remove', item, index);
      }
      return {removeTodo}
    }
  }
</script>

<style lang="scss" scoped>

</style>