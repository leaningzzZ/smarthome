<template>
  <div id="app">
<!--    <HelloWorld msg="Welcome to Your Vue.js App"/>-->
    <!-- <design></design> -->
    <designnn />
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
// import design from "@/components/design";
import designnn from "@/components/designnn"
export default {
  name: 'App',
  components: {
    // HelloWorld,
    // design
    designnn
  }
}
</script>

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
