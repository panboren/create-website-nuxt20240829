<template>
  <div class="edit">
    <Editor v-if="show" v-model="state" :formData="formData"></Editor>
  </div>
</template>

<script setup lang="ts">
import { ref, provide } from 'vue'
import data from './data.json'
import Editor from './packages/editor'
import { registerConfig as config } from './utils/editor-config'
// import Range from './components/Range.jsx'

// 禁用默认的 layout
definePageMeta({
  layout: false
})
const state = ref(data)
let show = ref(false)
provide('config', config) // 将组件的配置直接传值
const formData = ref({
  username: 'zfjg',
  password: 123,
  start: 0,
  end: 100
})
onMounted(()=>{
  console.log(999)
  show.value = true
  console.log(9991,show)
})
</script>

<style lang="scss">
.edit {
  position: fixed;
  top: 20px;
  left: 20px;
  right: 20px;
  bottom: 20px;
}
</style>
