<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" @click="changeOne">
    <!-- <div @click="goChild()">点我编程式跳转路由</div>
    <div @click="goChild()">点我声明式跳转路由</div> -->
    {{name}}
    {{age}}
    {{info.a}}
    {{info.b}}
  </div>
</template>

<script>
import { reactive, toRefs } from '@vue/reactivity'
// import router from '@/router'
//传递参数的页面
export default {

  setup() {
    let obj = reactive({
      name: '张三',
      age: 18,
      info: {
        a: 'aaaa',
        b: 'bbbb'
      }
    })
    function changeOne() {
      obj.info.a += '1'
    }
    const { name, age } = toRefs(obj)
    // setInterval(() => {
    //   name.value += '啾啾丸'
    //   // console.log(name.value);
    // }, 1000);
    // const router = useRouter()
    // let nums = 123
    // function goChild() {
    //   router.push({ path: 'childRouter', query: { nums } })
    // }
    return {
      name,
      age,
      ...toRefs(obj),
      changeOne
      // goChild,
    }
  }
}
</script>
