<template>

  <h1>{{ msg }}</h1>
  <button @click="handleClick">count is: {{ count }}</button>
  <h1>{{ fullName }}</h1>
  <h1 v-for="framework in upperFrameworks" :key="framework">{{ framework }}</h1>
</template>

<script>
import { ref, reactive, computed, watchEffect ,watch} from 'vue';

export default {
  name: 'HelloWorld',

  props : {
    message:{
      type:String,
    }
  },

  setup(props,{emit,attrs,slots}) {

    const msg = 'Hello Vue 3.0 + Vite';
    const count = ref(5);

    const user = reactive({ name: 'tofiq', last: 'hamzai' });
    const frameworks = reactive(['vue.js', 'angular']);

    const upperFrameworks = computed(() => frameworks.map(framework => framework.toUpperCase()));

    const fullName = computed({
      get: () => user.name + ' ' + user.last,
      set: (value) => {

        // const userFullName = value.split(' ');
        // user.name = userFullName[0];
        // user.last = userFullName[1];
        const [name, last] = value.split(' ');
        user.name = name;
        user.last = last;
      }
    })

    watch(()=>user.name,(newName,oldName)=>{
      // console.log(newName,oldName)
    })


    fullName.value = 'mamad mohammadi';



    watchEffect((onInvalidate) => {
      // console.log('count', count.value);

      // const fetching =

      // DOM and template refs

      onInvalidate(() => {
        // side effect
        // fetching.cancel()
      })
    });


    // const stopWatchEffect = watchEffect(() => {
    //   console.log('count', count.value)
    // });

    // stopWatchEffect()


    // function handleClick() {
    //   count.value++;
    //   this
    // }
    const handleClick = () => {
      count.value++;
    }


    return {
      msg,
      count,
      user,
      upperFrameworks,
      fullName,
      handleClick
    }
  },

  // beforeCreate()
  // created

  // data() {
  //   return {
  //     count: 0,
  //     msg: 'Hello Vue 3.0 + Vite'
  //   }
  // }

  computed: {
    fullName: {
      // getter
      get() {
        return this.firstName + ' ' + this.lastName
      },
      // setter
      set(newValue) {
        console.log(newValue)
        const names = newValue.split(' ')
        this.firstName = names[0]
        this.lastName = names[names.length - 1]
      }
    }
  },

  fullName : "mamad ch",

  /* computed: {
    fullName: {
      get() {
        return this.user.name + ' ' + this.user.last;
      },
      set(newValue) {
        const fullName = newValue.split(' ');
        this.user.name = fullName[0];
        this.user.last = fullName[1];
      }
    },
    upperFrameworks: function() {
      return this.frameworks.map(framework => framework.toUpperCase())
    }
  }, */
}
</script>
