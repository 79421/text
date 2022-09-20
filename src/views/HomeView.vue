<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" @click="add()">
    <div>{{obj.name}}</div>
    <div>{{count}}</div>
  </div>
</template>

<script>
import HelloWorld from '@/components/HelloWorld.vue'
import { ref, reactive } from 'vue'
export default {
  name: 'HomeView',
  setup() {
    let count = ref(100)
    const add = () => {
      obj.name = '啾啾丸天下无双(master)(a分支)'
    }
    let obj = reactive({
      name: '啾啾丸',
      age: 18
    })
    console.log(ref);
    return {
      obj,
      count,
      add
    }
  },
  components: {
    HelloWorld
  }
}
</script>
