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
export default {
  name: "App",
  data() {
    return {
      username: "",
      password: "",
    };
  },
  methods: {
    sumbmitForm(){
      // e.preventDefault();
      // console.log('제출됨')
      const data = {
        username: this.username,
        password: this.password
      }
      
      axios.post('https://jsonplaceholder.typicode.com/users/', data)
      .then((res)=>{
        console.log(res);
      });

      // this.username;
      // this.password;
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
