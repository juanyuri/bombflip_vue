<!-- 
    It represents a single card component that can be flipped to reveal a number or a Bomb.
-->

<template>

</template>

<script setup>
import {ref} from 'vue'

let isHidden = ref(true)
let isSuspicious = ref(false)
console.log(isHidden + isSuspicious)

</script>