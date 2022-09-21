<template>
  我是子组件
  {{ props.name }}
  <button @click="JiuJiu">向父组件传值</button>
</template>

<script>
export default {
  name: 'helloChild',
  props: ['name'],
  setup(props, context) {
    let num = 250
    let JiuJiu = () => {
      context.emit("ziDingYi", num)
    }
    return {
      props,
      JiuJiu
    }
  },
}
</script>

<style scoped>

</style>
