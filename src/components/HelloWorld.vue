<template>
  <h1>{{ count }}</h1>
  <h1>{{ double }}</h1>
  <button @click="increase" style="margin-bottom: 15px">+1</button>
</template>

<script>
import {ref,computed} from "vue";

export default {
  setup(){
    // ref 是一个函数，它接受一个参数，返回的就是一个神奇的 响应式对象 。我们初始化的这个 0 作为参数包裹到这个对象中去，在未来可以检测到改变并作出对应的相应。
    const count = ref(0)
    const double = computed(() => {
      return count.value * 2
    })
    const increase = () => {
      count.value++
    }
    return {
      count,
      increase,
      double
    }
  }
}
</script>
