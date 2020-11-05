<template>
  <div class="wrapper">
    <span v-if="isOpen">开</span>
    <span v-else>关</span>
    <button @click="toggleOpen">开关</button>
  </div>
</template>

<script lang="ts">
import {defineComponent,ref} from "vue"

export interface ColumnProps {
  id:number;
  title:string;
  description:string;
}
export default defineComponent({
  name:"Dropdown",
  setup(){


    const isOpen = ref(true);
    const toggleOpen = ()=>{
      isOpen.value =!isOpen.value
    }


    return {
      toggleOpen,
      isOpen
    }
  }
})
</script>

<style scoped>

</style>
