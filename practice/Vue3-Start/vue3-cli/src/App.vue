<template>
  <AppHeader :appTitle="message" @change="changeMessage"/>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
</template>

<script>
// import 라이브러리 from '라이브러리 이름'
// import 파일이름 from '상대경로'
import HelloWorld from './components/HelloWorld.vue'
import AppHeader from './components/AppHeader.vue'
export default {
  // 인스턴스 옵션 속성
  name: 'App',
  components: {
    HelloWorld,
    AppHeader
  },
  data(){
    return {
      message: 'App Header Component'
    }
  },
  methods:{
    changeMessage(){
      this.message = '변경된 App Header'
    }
  }
}
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
