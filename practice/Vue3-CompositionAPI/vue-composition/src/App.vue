<template>
  <div>
    <p>{{ message }}</p>
    <button @click="changeMessage" />
  </div>
</template>

<script>
import {useMessage} from './composable/useMessage'
export default {
  setup(){
    const {message,changeMessage} = useMessage();
    return {message, changeMessage}
  }
}
</script>

<style lang="scss" scoped>

</style>