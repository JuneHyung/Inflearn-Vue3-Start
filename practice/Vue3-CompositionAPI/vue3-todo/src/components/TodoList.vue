<template>
  <ul>
    <li v-for="(item, idx) in todoItems" :key="idx">
      <span>{{ item }}</span>
      <button @click="removeTodo(item, idx)">삭제</button>
    </li>
  </ul>  
</template>

<script>
  export default {
    props: ['todoItems'],
    setup(porops, context){
      function removeTodo(item, idx){
        context.emit('remove', item, idx)
      }
      return {removeTodo}
    }
  }
</script>