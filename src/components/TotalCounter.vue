<template>
    <div>TotalCounter</div>
    <input type="number" v-model="contador">
    <p>{{ contador }}</p>
</template>
  
<script setup>
import { ref } from 'vue';
import { computed } from 'vue';


let counter = ref(0)

const contador = computed({
    get() {
        return counter.value
    },
    set(newValue){
        const newCounter = Number(newValue)
        if(!isNaN(newCounter)){
            counter.value = newCounter
        }
    }
})
</script>
  
<style scoped>
</style>
  