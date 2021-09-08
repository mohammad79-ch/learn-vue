<template>
  <input type="text" class="input is-rounded"
  :class="{
    [`is-${color}`]:color
  }"
  v-bind="$attrs"
  :value="modelValue"
  @input="(event) =>$emit('update:modelValue',event.target.value)"
   >

</template>

<script>
export default {
  name : 'BaseInput',
  inheritAttrs : false,
  props : {
    color:{
      type:String,
      required : false
    },
    modelValue : {
      type : [String,Number]
    }
  },
}
</script>

<style lang="scss">
@import "bulma/sass/utilities/_all.sass";
@import "bulma/sass/helpers/spacing.sass";
@import "bulma/sass/form/shared.sass";
@import "bulma/sass/form/tools.sass";
@import "bulma/sass/form/input-textarea.sass";
</style>