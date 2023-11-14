<template>
  <h1>{{ App Title }}</h1>
  <button @click="changeTitle">변경</button>
</template>

<script>
  export default {
    props: ['appTitle'],
    methods: {
      changeTitle(){
        this.$emit('change')
      }
    }
  }
</script>
<style></style>