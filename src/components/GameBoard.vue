<!-- 
    It represents the main playing area with rows and columns where cards are placed
-->

<template>
    <div id="gameContainer">
        <p>Nivel: {{ level }}</p>
        <p>Num Doses: {{ levels_info[level][0]["num_two"] }}</p>
        <p>Num Threes: {{ levels_info[level][0]["num_three"] }}</p>
        <p>Num Bombs: {{ levels_info[level][0]["num_bombs"] }}</p>
    </div>
</template>

<script setup>
import {ref} from 'vue'
import levels from '@/data/levels.json';

const level = ref(1)
let levels_info = levels[0]

console.log(levels_info)

</script>