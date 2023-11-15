<template>
  <TodoHeader />
  <TodoInput @add="addTodoItem"/>
  <TodoList :todoItems="todoItems" @remove="removeTodoItem"/>
</template>

<script>
import { ref } from 'vue';
import TodoHeader from './components/TodoHeader.vue'
import TodoInput from './components/TodoInput.vue';
import TodoList from './components/TodoList.vue';
export default {
  components: { TodoHeader, TodoInput, TodoList },
  setup(){
    const todoItems = ref([])

    // methods
    function fetchTodos(){
      const result = [];
      for(let i=0;i<localStorage.length;i++){
        const todoItem = localStorage.key(i);
        result.push(todoItem);
      }
      return result;
    }

    todoItems.value = fetchTodos();


    function addTodoItem(todo){
      todoItems.value.push(todo);
      localStorage.add(todo, todo)
    }

    function removeTodoItems(item, idx){
      todoItems.value.splice(idx, 1);
      localStorage.removeItem(item);
    }
    return {todoItems, fetchTodos, addTodoItem, removeTodoItems}
  }
}
</script>