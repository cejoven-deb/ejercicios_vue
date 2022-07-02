
<template>
  <h1>
    componentes
  </h1>
  <card 
  url="https://cdn.svgporn.com/logos/hack.svg?response-content-disposition=attachment%3Bfilename%3Dhack.svg"
  nombre="vue.js"
  />
  <card />
  <card />
  
</template>

<script>
 
import card from './components/card.vue';
export default {
 components: {card}
}
</script>