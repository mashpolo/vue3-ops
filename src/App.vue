<script setup lang="ts">
  import Child from './views/Child.vue'
  import { onMounted, ref } from 'vue'

  defineProps({
    msg: {
      type: String,
      default: ()=>{return "hello, world"}
    }
  })

  const handle = (params: string) => {
    console.log(params)
  }
  const child = ref()
  onMounted (() => {
    console.log(child.value.testChild())
  })
</script>

<template>
  <Child @on-change="handle" ref="child"></Child>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
