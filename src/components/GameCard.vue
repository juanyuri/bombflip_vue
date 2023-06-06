<!-- 
    It represents a single card component that can be flipped to reveal a number or a Bomb.
-->

<template>
    <p>{{ cardValue }}</p>
</template>

<script setup>
import { ref } from 'vue'
import { defineProps } from 'vue'

const props = defineProps(['cardValue'])
console.log(props)

let isHidden = ref(true)
let isSuspicious = ref(false)
console.log(isHidden.value + isSuspicious.value)

</script>