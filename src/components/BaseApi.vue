<template>
  <p>{{msg}}</p>
  <button @click="handleClick">Counter {{count}}</button>
</template>

<script>
import { ref } from 'vue'

export default {

name: "BaseApi",

  setup(){
  let msg = "Mohammad Ch";
  let count = ref(0);

  function handleClick(){
    count.value++
  }

  return{
    msg,
    count,
    handleClick
  }
  }
}
</script>

<style scoped>

</style>