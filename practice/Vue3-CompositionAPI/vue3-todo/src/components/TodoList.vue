<template>
  <ul>
    <li v-for="(item, idx) in todoItems" :key="idx">
      <span>{{ item }}</span>
      <button @click="removeTodo(item, idx)">삭제</button>
    </li>
  </ul>  
</template>

<script>
import { watch } from 'vue';
  export default {
    props: ['todoItems', 'userId'],
    setup(props, {emit}){
      function removeTodo(item, idx){
        emit('remove', item, idx)
      }

      watch(props.todoItems, (newValue)=>{
        console.log({newValue});
      });
      return {removeTodo}
    }
  }
</script>