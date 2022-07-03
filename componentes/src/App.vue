
<template>
  <h1>
    componentes
  </h1>
  <card 
  url="https://cdn.svgporn.com/logos/hack.svg?response-content-disposition=attachment%3Bfilename%3Dhack.svg"
  nombre="vue.js"
  />
  <card
  url="https://cdn.svgporn.com/logos/archlinux.svg?response-content-disposition=attachment%3Bfilename%3Darchlinux.svg"
  nombre="ArchLinux.js"
  />
  <card
  url="https://cdn.svgporn.com/logos/debian.svg?response-content-disposition=attachment%3Bfilename%3Ddebian.svg"
  nombre="Debian.js"
 />
  
</template>

<script>
 
import card from './components/card.vue';
export default {
 components: {card}
}
</script>