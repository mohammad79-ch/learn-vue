<template>
  <!--  <BaseButton color="info" is-light="false" />-->
  <!--  <BaseButton color="danger" is-light="false" is-large="large" />-->
  <!--  <BaseButton color="warning" is-loading="true" is-light="false" is-large="large" />-->
  <!--    <BaseButton color="primary" :is-loading="isLoading"  is-large="small" @click="changeColor" />-->

  <!--  base input -->

<!--  <BaseInput color="danger"/>-->
<!--  <BaseInput color="primary"/>-->
<!--  <BaseInput color="warning" v-model="age"/>-->
<!--  <BaseInput color="warning" v-model="name"/>-->
<!--  <BaseInput color="dark" type/>-->
<!--  <p>{{ name }}</p>-->

<!--  bade select-->

    <BaseSelect />

</template>

<script>

// import BaseButton from "./components/BaseButton.vue";
import BaseInput from "./components/BaseInput.vue";
import BaseSelect from "./components/BaseSelect.vue";

export default {
  name: 'App',
  components: {
    // BaseButton
    BaseInput,
    BaseSelect
  },

  data() {
    return {
      isLoading: false,
      name: "mamad",
      age: 21,
      type: "password",
    }
  },


  methods: {

    changeColor() {
      this.isLoading = true
    }
  }
}
</script>
