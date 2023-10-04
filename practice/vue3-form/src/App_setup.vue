<template>
  <form action="" @submit.prevent="submitForm">
    <div>
      <label for="userId">ID : </label>
      <input id="userId" type="text" v-model="username" />
    </div>
    <div>
      <label for="password">PW : </label>
      <input id="password" type="password" v-model="password" />
    </div>
    <button type="submit">LOGIN</button>
  </form>
</template>

<script>
import axios from 'axios';
import { ref } from 'vue';
export default {
  name: "AppSetup",
  setup(){
    const username = ref('');
    const password = ref('');

    // methods
    const submitForm=()=>{
      // e.preventDefault();
      // console.log('제출됨')
      const data = {
        username: username.value,
        password: password.value
      }
      
      axios.post('https://jsonplaceholder.typicode.com/users/', data)
      .then((res)=>{
        console.log(res);
      });
    }
    return {
      username,
      password,
      submitForm
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
