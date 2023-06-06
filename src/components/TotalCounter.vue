<template>
    <div>TotalCounter</div>
    <input type="number" v-model="contador">
</template>
  
<script setup>
import { ref } from 'vue';
import { computed } from 'vue';


let counter = ref(0)

/* writable computed property */
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
  