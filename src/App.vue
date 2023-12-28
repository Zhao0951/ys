<template>
  <h1>原神</h1>
  <ys/>
</template>

<script lang="ts">
  // 引入其他组件
  import ys from './components/ys.vue'
  // 默认暴露
  export default {
    name: 'APP', // 组件名
    components: {ys} // 注册组件
  }
</script>

<style>
  h1{
    padding: 10px;
    text-align: center;
  }
</style>