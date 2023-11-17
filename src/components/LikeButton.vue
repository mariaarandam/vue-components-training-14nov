
<script setup>
import { ref } from 'vue';

    const likes = ref(0)
    let indexColor = 0

    const colors = ['purple','blue','green','yellow','orange','red']

    const incrementsLikes = () => {
        likes.value++
        indexColor.value++

        if(indexColor == colors.length){
            indexColor = 0
        }
    }
</script>


<template>
    <button v-bind:style="{ backgroundColor: colors[likes % colors.length] }" v-on:click="incrementsLikes">{{ likes }} Like</button>
</template>


<style scoped>
</style>