<template>
    <img src="../assets/img123.png" class="img">
</template>


<script>
//接受参数的页面
import { useRoute } from 'vue-router'
export default {
    setup() {
        const route = useRoute()
        console.log(route.query.nums);
    }
}
</script>

<style>
.img {
    width: 500px;
    height: 300px;
}
</style>