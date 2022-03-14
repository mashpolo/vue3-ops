<script setup>
import { ref } from 'vue'

defineProps({
  msg: String,
  default: ()=>{return "hello, child"}
})
props: []
const msg = ref('hello')
const testChild = ()=> {
  // this.msg = "hey, call ok"
  msg.value = 'iiii'
  console.log('hello, child ref child')
  return 0
}

const emit = defineEmits(['on-change'])
const handle = () => {
  emit('on-change', 'child methods')
}
defineExpose({
  testChild,
  tetChild2
})

</script>

<template>
  <p>{{ msg }}</p>
  <button @click="handle">click</button>
</template>

<style scoped>
a {
  color: #42b983;
}
</style>
