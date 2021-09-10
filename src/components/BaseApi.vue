<template>
  <p @click="handleName">{{user.name}}</p>
  <button @click="handleClick">Counter {{count}}</button>
</template>

<script>
import { ref, reactive,computed} from 'vue'

export default {

name: "BaseApi",

  setup(){

  let count = ref(0);

  const user = reactive({name : "Mamads"})

  function handleClick(){
    count.value++
  }

  const frameworks = reactive(['laravel','vue']);

  const upperComputed = computed(()=> frameworks.map(framework => framework.toUpperCase()))

    console.log(upperComputed)
    function handleName(){
     user.name = "Programmer"
    }

  return{
    count,
    user,
    upperComputed,
    handleClick,
    handleName,
  }

  }
}
</script>

<style scoped>

</style>