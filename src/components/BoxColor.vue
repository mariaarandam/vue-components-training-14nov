<script setup>
import { callWithAsyncErrorHandling } from 'vue';

const props = defineProps(['r', 'g', 'b'])

function rgbToHex(r, g, b) {
    const componentToHex = (c) => {
        const hex = c.toString(16);
        return hex.length === 1 ? '0' + hex : hex;
    };

    const red = componentToHex(r);
    const green = componentToHex(g);
    const blue = componentToHex(b);

    return '#' + red + green + blue;
}

/* 
Detectar si el color de fondo es oscuro o callWithAsyncErrorHandling, y cambiar el color del texto
*/
function whiteOrBlack(r, g, b) {
    if (r < 128 || g < 128 || b < 128) {
        return "white"
    }

    return "black"
}

</script>

<!-- Reto

    1. Codifica el BoxColor.vue para que se muestre el cada uno de los valores de los colores en el lugar adecuado
   2. Necesitarás definir las propiedades con defineProps (mirad ejemplos anteriores en este mismo proyecto)
   3. Buscad por inet una forma (función o computed property) de pasar de un color en formato RGB a hexadecimal

    Corregir el 3 a las 10.02

-->

<template>
<!-- Reto: haced que el atributo style sea dinámico. Estableced el color de backgroundColor con el valor que devuelve la functión rgbToHex -->
<div :style="{backgroundColor: rgbToHex(r,g,b), color: whiteOrBlack(r, g, b) }" class="container">
    <div>
        rgb ({{ r }}, {{ g }}, {{ b }})
    </div>
    <div>
        {{ rgbToHex(r, g, b) }}
    </div>
</div>
    
</template>

<style scoped>
div.container {
    border: 1px solid black;
    padding: 3rem;
    margin-top: .75rem;
    max-width: 500px;
    text-align: center;
    font-size: 1.5rem;
}
</style>