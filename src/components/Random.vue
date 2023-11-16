<script setup>
const props = defineProps(['min', 'max'])

</script>

<template>
  <div>
    Random value between {{ min }} and {{ max }} = {{ (parseInt(Math.random() * max) + min) }}

        

  </div>
</template>

<style scoped>
div{
    border: 1px solid black;
    padding: 1rem;
    margin-top: .75rem;
    max-width: 500px;
}
</style>