<template>
  <TodoHeader :appTitle="title"/>
  <TodoInput @add="addTodoItem"/>
  <TodoList :todoItems="todoItems" @remove="removeTodoItem"/>
</template>

<script>
import { onBeforeMount, ref } from 'vue';
import TodoHeader from './components/TodoHeader.vue'
import TodoInput from './components/TodoInput.vue';
import TodoList from './components/TodoList.vue';
import {useTodo} from './hooks/useTodo';
export default {
  components: { TodoHeader, TodoInput, TodoList },
  setup(){
    const {todoItems, addTodoItem, fetchTodos} = useTodo();
    const title= ref('할일 앱');

    function removeTodoItem(item, idx){
      todoItems.value.splice(idx, 1);
      localStorage.removeItem(item);
    }

    
    onBeforeMount(()=>{
      todoItems.value = fetchTodos();
    })

    return {todoItems, addTodoItem, removeTodoItem, title}
  }
}
</script>