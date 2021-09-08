<template>
  <button
      class="button"  :class="{ [`is-${color}`]:color,
      [`is-${isLarge}`] : isLight,
      'is-large' : isLarge,
      'is-loading': isLoading
  }"
  >Click</button>
</template>

<script>
export default {
name: "BaseButton",

  props : {
    color : {
      type : String,
      required : false
    },
    isLight:{
      type:Boolean,
      default : false
    },
    isLarge : {
      type: String,
      default : false
    },
    isLoading : {
      type : String,
      default : false
    },
  },


}
</script>

<style lang="scss">
  @import "bulma/sass/utilities/_all.sass";
  @import "bulma/sass/elements/button.sass";
</style>