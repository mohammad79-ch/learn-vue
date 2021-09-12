<template>
  <button @click="showP = false" ref="btn">Click me pls</button>
  <p v-if="showP">Test</p>
</template>

<script>
import {
  onBeforeMount,
  onMounted,
  onBeforeUpdate,
  onUpdated,
  onBeforeUnmount,
  onUnmounted,
  onActivated,
  onDeactivated,
  onErrorCaptured,
  ref
} from "vue";

export default {
  name: "LifeCycle",

  data() {
    return {
      Name: '',
      showP: true
    }
  },
  setup() {

    const btn = ref(null)


    onBeforeMount(() => {
      console.log("Before Mount!");
    });
    onMounted(() => {

      setTimeout(()=>{
        console.log(btn.value.click())
      },3000)

      console.log("Mounted!");
    });
    onBeforeUpdate(() => {
      console.log("Before Update!");
    });
    onUpdated(() => {
      console.log("Updated!");
    });
    onBeforeUnmount(() => {
      console.log("Before Unmount!");
    });
    onUnmounted(() => {
      console.log("Unmounted!");
    });
    onActivated(() => {
      console.log("Activated!");
    });
    onDeactivated(() => {
      console.log("Deactivated!");
    });
    onErrorCaptured(() => {
      console.log("Error Captured!");
    });

    return {
      btn
    }

  },

}
</script>
