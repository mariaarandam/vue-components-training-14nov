<script setup>

import IdCard from './components/IdCard.vue';
import Random from './components/Random.vue';
import BoxColor from './components/BoxColor.vue';
import LikeButton from './components/LikeButton.vue';



</script>

<template>
  <h1>Creación de componentes con Vue</h1>
  <section>
    <h2>Id Card</h2>
    <IdCard last-name='Doe' first-name='John' gender='male' :height="178" :birth='new Date("1992-07-14")'
      picture="https://randomuser.me/api/portraits/men/44.jpg" />

    <IdCard
    last-name='Delores '
    first-name='Obrien'
    gender='female'
    :height="172"
    :birth='new Date("1988-05-11")'
    picture="https://randomuser.me/api/portraits/women/44.jpg"
/>
  </section>

  <section>
    <h2>Random</h2>
      <Random :min="1" :max="6" />
      <Random :min="1" :max="100" /> 
      <Random :min="100" :max="1000" /> 
  </section>

  <section>
    <h2>BoxColor</h2>
      <BoxColor :r="255" :g="0" :b="0" />
      <BoxColor :r="128"
       :g="255" :b="0" />
      <BoxColor :r="0" :g="120" :b="0" />
      <BoxColor :r="255" :g="129" :b="129" />
  </section>

  <section>
    <h2>State</h2>
      <LikeButton likes/>
      <LikeButton likes/>
  </section>

</template>

<style scoped>
h2 {
  color: blueviolet;
  margin-top: 2rem;
}
</style>
  