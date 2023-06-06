<!-- 
    It represents the main playing area with rows and columns where cards are placed
-->

<template>
    <div id="gameContainer">
        <p>Nivel: {{ level }}</p>
        <p>{{ level_data }}</p>

    <!-- Tablero -->
    <div class="board">
      <div v-for="(row, rowIndex) in board" :key="'row-' + rowIndex" class="board-row">
        <GameCard
          v-for="(cell, colIndex) in row"
          :key="'cell-' + rowIndex + '-' + colIndex"
          :cardValue="cell"
          :class="'cell-' + rowIndex + '-' + colIndex"
        />
      </div>
    </div>
    </div>
</template>

<script setup>
import { ref } from 'vue'
import { defineExpose } from 'vue';
import GameCard from "@/components/GameCard.vue"

defineExpose({ components: { GameCard }})

import levels from '@/data/levels.json';
/* import GameBoard from './components/GameCard.vue' */

let levels_info = levels[0]
const level = ref(1)
const level_data = levels_info[level.value][0]
const board = ref([])


const initBoard = () => {
    const newBoard = fillWithValues(level_data);

    //Logic to populate cells based on specific rules and the current level.

    board.value = newBoard
    console.log(board.value)
}


const fillWithValues = (level) => {

    // Create a flat array (spread operator) with all the necessary values.
    const values = [
        ...Array(level.num_two).fill(2),
        ...Array(level.num_three).fill(3),
        ...Array(level.num_bombs).fill(-1)
    ]

    // Filling the rest with 1s
    while ( values.length < 25 ) values.push(1)

    shuffle(values)

    // Convert the shuffled flat array into a grid of 5x5
    return chunck(values)
}



// Fisher-Yates Shuffle.algorithm implementation to randomize an array
const shuffle = (array) => {
    for(let i= array.length -1 ;i>0;--i){
       const j=Math.floor(Math.random() * (i+1));
       [array[i],array[j]] =[array[j],array[i]];
   }
}


// Function to split a given array into chunks of 5x5 as sub arrays
const chunck = (cardValues) => {
    let size = 5
    let chunks = []

    for (let i = 0; i < cardValues.length; i += size) {
        // Extract a subarray of size 'size' from the current index and add it to 'chunks'
        const subArray = cardValues.slice(i, i + size);
        chunks.push(subArray);
    }
    
    return chunks
}

initBoard()
</script>



<style scoped>
.board {
  display: grid;
  grid-template-columns: repeat(5, auto);
}
.board-row {
  display: contents;
}
</style>