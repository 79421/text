<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" @click="add()">
    <div>{{obj.name}}</div>
    <div>{{count}}</div>
    {{a}}
    <helloChild :name="obj.name" @ziDingYi="JJJ" />
  </div>
</template>

<script>
import { ref, reactive, onBeforeMount, onMounted, onUpdated, onBeforeUpdate, onBeforeUnmount } from 'vue'
import helloChild from "../components/helloChild.vue"
export default {
  name: 'HomeView',
  setup() {
    //响应式数据
    let count = ref(100)
    //子组件传来的值
    let a = ref(0)
    //修改页面数据
    const add = () => {
      obj.name = '啾啾丸天下无双(master)(a分支)'
    }
    //定义一个
    let obj = reactive({
      name: '啾啾丸',
      age: 18
    })
    //子传父（接收）
    function JJJ(num) {
      a.value = num
    }
    //生命周期函数
    onBeforeMount(() => {
      console.log('onBeforeMount');
    })
    onMounted(() => {
      console.log('onMounted');
    })
    onBeforeUpdate(() => {
      console.log('onBeforeUpdate');
    })
    onUpdated(() => {
      console.log('onUpdated');
    })
    onBeforeUnmount(() => {
      console.log('onBeforeUnmount');
    })
    onUnmounted(() => {
      console.log('onUnmounted');
    })

    return {
      obj,
      count,
      add,
      JJJ,
      a
    }
  },
  components: {
    helloChild
  }
}
</script>
