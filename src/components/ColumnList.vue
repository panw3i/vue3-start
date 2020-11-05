<template>
<ul>
  <li v-for="item in list" :key="item.description" >{{item.description}}</li>
</ul>
</template>

<script lang="ts">
// eslint-disable-next-line no-unused-vars
import {defineComponent,PropType} from "vue"

export interface ColumnProps {
  id:number;
  title:string;
  description:string;
}
export default defineComponent({
  name:"ColumnList",
  props:{
    list:{
      type:Array as PropType<ColumnProps[]>,  // 类型判言
      required:true,
    }
  }
})
</script>

<style scoped>

</style>
