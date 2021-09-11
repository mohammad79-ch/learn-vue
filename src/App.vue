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

<!--    <BaseSelect :items="data" color="danger" v-model="selectedOption"/>-->

        <BaseApi message="Hello World" />

</template>

<script>

// import BaseButton from "./components/BaseButton.vue";
import BaseInput from "./components/BaseInput.vue";
import BaseApi from "./components/BaseApi.vue";
import BaseSelect from "./components/BaseSelect.vue";

export default {
  name: 'App',
  components: {
    // BaseButton
    BaseInput,
    BaseSelect,
    BaseApi
  },

  data() {
    return {
      isLoading: false,
      name: "mamad",
      age: 21,
      type: "password",
      data : [
        {key:1,value:'mamad'},
        {key:2,value:'ali'},
        {key:3,value:'Amir'},
      ],
      selectedOption : 1
    }
  },


  methods: {

    changeColor() {
      this.isLoading = true
    }
  }
}
</script>
