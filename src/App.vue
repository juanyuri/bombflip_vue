<template>
  <TotalCounter />
  <GameBoard />
</template>

<script>
import TotalCounter from './components/TotalCounter.vue'
import GameBoard from './components/GameBoard.vue'

export default {
  name: 'BombFlip',
  components: {
    TotalCounter, GameBoard
  }
}
</script>

<style>
</style>
