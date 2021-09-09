<template>
  <div class="select" v-bind="$attrs" :class="{[`is-${color}`]:color}">
  <select  @change="(event)=>$emit('update:modelValue',event.target.value)">
    <option  v-for="item in items" :key="item.key" value="1" :selected="item.key === modelValue"  >
      {{item.value}}
    </option>
  </select>
  </div>
</template>

<script>
export default {
name: "BaseSelect",
  inheritAttrs : false,
  props :{
  items :{
    type : Array,
    required : false
  },
    modelValue : {
      type : [String,Number]
    },
    color :{
    type:String,
    }
  }

}

</script>

<style lang="scss">
@import "bulma/sass/utilities/_all.sass";
@import "bulma/sass/helpers/spacing.sass";
@import "bulma/sass/form/shared.sass";
@import "bulma/sass/form/tools.sass";
@import "bulma/sass/form/select.sass";
</style>