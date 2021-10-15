<template>
  <HelloWorld msg="Hello Vue 3 + Vite" />
  <ThreeDMagic />
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import ThreeDMagic from './components/ThreeDMagic.vue'

export default {
  components: {
    HelloWorld,
    ThreeDMagic
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
