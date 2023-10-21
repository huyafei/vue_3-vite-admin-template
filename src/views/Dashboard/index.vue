<!--
 * @Name: index.vue
 * @Description:
 * @Date: 2023/10/20 16:31
 * @Author: huyafei
 * @LastEditors: huyafei
 * @LastEditTime: 2023/10/20 16:31
-->
<script setup>
import {
  ref,
  reactive,
  computed,
  watch,
  onMounted,
  onBeforeUnmount,
  toRefs,
  getCurrentInstance
} from 'vue'

const props = defineProps([])
const emit = defineEmits([])

const _this = getCurrentInstance().proxy
console.log(_this)
const n = reactive({
  a: 1,
  b: 2
})
// 一个计算属性 ref 格式
const sum = computed(() => {
  return n.a + n.b
})
watch(sum, (val, oldVal) => {
  console.log(val, oldVal)
})
onMounted(() => {
  console.log('mounted')
})
</script>
<template>
  <div> 首页 </div>
</template>
<style scoped></style>
