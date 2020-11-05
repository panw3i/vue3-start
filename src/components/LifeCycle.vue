<template>
  <div class="wrapper">
    <label>
      <input type="text" ref="inputRef" @input="handleChange"/>
    </label>
    <h1>{{inputValue}}</h1>
  </div>
</template>

<script lang="ts">
import {defineComponent,onMounted,onUnmounted,ref} from "vue"

export interface ColumnProps {
  id:number;
  title:string;
  description:string;
}
export default defineComponent({
  name:"LifeCycle",
  setup(){
    onMounted(()=>{
      document.addEventListener("click", ()=>{
        console.log("document click")
      })
    })

    onUnmounted(()=>{
      document.removeEventListener("click",()=>{
        console.log("remove document click")
      })
    })

    let inputValue = ref("");


    // input event
    const handleChange=(e:null | MouseEvent)=>{
      if (e !==null){
        let element = e.target as HTMLInputElement   // input element type
        console.log('e.target.value',element.value)
        inputValue.value = element.value
      }
    }

    // export value
    return {
      handleChange,
      inputValue
    }


  }
})
</script>

<style scoped>

</style>
