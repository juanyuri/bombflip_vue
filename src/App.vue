<template>
  <TotalCounter />
  <HelloWorld />
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import TotalCounter from './components/TotalCounter.vue'

export default {
  name: 'BombFlip',
  components: {
    HelloWorld, TotalCounter
  }
}
</script>

<style>
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
