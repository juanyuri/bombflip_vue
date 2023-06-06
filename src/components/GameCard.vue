<!-- 
    It represents a single card component that can be flipped to reveal a number or a Bomb.
-->

<template>
    <div class="cell">
        {{ cardValue }}
    </div>
</template>

<script setup>
import { ref } from 'vue'
import { defineProps } from 'vue'

defineProps(['cardValue'])

let isHidden = ref(true)
let isSuspicious = ref(false)
console.log(isHidden.value )
console.log(isSuspicious.value )

</script>






<style scoped>

.cell{
    box-sizing: border-box;
    width:var(--width-casilla);
    height:var(--height-casilla);
    margin-right:15px;
    margin-top:15px;
    background-color: var(--casilla-color);
    color:var(--fuente-color);
    font-weight: bold;
    /* text-align: center; */
    /* line-height: var(--height-casilla); */
    font-size: var(--fuente-casilla);
    border-radius: var(--rounding);
    /* vertical-align: middle; */
    transition-duration: 150ms;
    transition-property: background-color;
    /* transform: rotateY(-180deg); */
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;  
    animation: 1.20s ease-out 0s 1 flipearCasillaINICIO;
}

.isHidden:hover{
    background-color: var(--casilla-hover-color);
    transition: 0.25s;
}

.isHidden.flipped-bomb{
    background-color: var(--fallo);
    transition: 0.85s;
    animation: 0.85s ease 0s flipearCasilla;
    -webkit-animation: flipearCasilla 1.0s forwards;
    animation: temblar 0.85s;
}

.isHidden.flipped{
    background-color: var(--casilla-focus-color);
    color:white;
    transition: 0.85s;
    animation: 0.85s ease 0s flipearCasilla;
    -webkit-animation: flipearCasilla 1.0s forwards;
}

.isHidden.flipped .numero{
    color: white;
    animation: 1.05s ease-in 0s aparecerNumeroCasilla;
    -webkit-animation: aparecerNumeroCasilla 1.05s forwards;
}

.isHidden.flipped-bomb .numero{
    color: white;
    animation: 1.05s ease-in 0s aparecerNumeroCasilla;
    -webkit-animation: aparecerNumeroCasilla 1.05s forwards;
}
</style>