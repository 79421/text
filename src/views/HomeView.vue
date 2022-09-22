<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" @click="changeOne">
    {{a.name}}
    {{a.info.age}}
  </div>
</template>

<script>
import { reactive, readonly, toRefs } from '@vue/reactivity'
//传递参数的页面
export default {
  setup() {
    let data = reactive({
      name: "啾啾丸", info: {
        age: 18
      }
    })
    let a = readonly(data)
    function changeOne() {
      a.name = '123'
      a.info.age = 2888
      console.log(a);
    }

    return {
      data,
      a,
      changeOne
    }
  }
}
</script>
