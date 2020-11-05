<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js + TypeScript App"/>
    <Dropdown/>
    <LifeCycle/>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src
import Dropdown from "@/components/Dropdown.vue";
import LifeCycle from "@/components/LifeCycle.vue";

@Options({
  components: {
    HelloWorld,
    Dropdown,
    LifeCycle,
  },
})
export default class Home extends Vue {}
</script>
