<template>
  <BaseButton color="info" is-light="false" />
  <BaseButton color="danger" is-light="false" is-large="large" />
  <BaseButton color="warning" is-loading="true" is-light="false" is-large="large" />
    <BaseButton color="primary" :is-loading="isLoading"  is-large="small" @click="changeColor" />
</template>

<script>

import BaseButton from "./components/BaseButton.vue";

export default {
  name: 'App',
  components: {
    BaseButton
  },

  data(){
    return {
      isLoading :false
    }
  },

  methods : {
    changeColor(){
      this.isLoading=true
    }
  }
}
</script>
