<template>
  <h1>{{ a }}</h1>
  <h1>{{ b }}</h1>
  <button @click="className">点击</button>
</template>

<script lang="ts">
  let i = {
    ys1: {
      name: '胡桃',
      age: '17'
    },
    ys2: {
      name: '甘雨',
      age: '2000'
    },
    ys3: {
      name: '魈',
      age: '2000'
    }
  }
  let ys = Object.values(i);
  export default {
    nome: 'ys',
    // vue2中的data和methode可以通过this拿到vue3中的setup中的数据
    // vue3中的setup不能拿到vue2中的data和methode中的数据

    // setup(){
    //   // setup中的this是undefined
    //   // 数据 vue2中是写在data中的 此时的数据不是响应式
    //   let a = `${ys[0].name}`;
    //   let b = `${ys[0].age}`;
    //   // 方法
    //   let index = 0;
    //   // 数据修改了 但不是响应式 页面不会发生变化
    //   function className(){
    //     index++;
    //     if(index > ys.length - 1){
    //       index = 0;
    //     }
    //     console.log(ys[index]);
    //     a = `${ys[index].name}`; 
    //     b = `${ys[index].age}`;
    //   }
    //   return { a, b, className }
    //   // 可以返回一个函数渲染给页面
    //   // return () => '原神'
    // }
  }
</script>

<script lang="ts" setup> // setup的语法糖 
  // 引入ref 用来定义基本类型和对象类型的响应式数据
  import { ref } from 'vue'
  // 用ref定义响应式的变量
  let a = ref(`${ys[0].name}`);
  let b = ref(`${ys[0].age}`);
  // 方法
  let index = 0;
  function className(){
    index++;
    if(index > ys.length - 1){
      index = 0;
    }
    // ref对象的value属性是响应式
    a.value = `${ys[index].name}`; 
    b.value = `${ys[index].age}`;
  }
</script>