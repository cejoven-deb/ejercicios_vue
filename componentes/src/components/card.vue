<template>
<Grid>
    
       <img :src="url" alt="nombre" /> 
       <h2>{{nombre}}</h2>
       <a 
       v-bind:href="url"
       target="_blank">

        Descargar
       </a> 
       <a 
       v-bind:href="url"
       target="_blank">

        Visitar
       </a> 

  
    </Grid>
</template>

<script>
import Grid from './Grid.vue';
export default {
    props: {
        url: {
            String,
        },
        nombre: {
            String,
        },
    },
    components: { Grid }
};
</script>
<style scoped>
img{
    width: 8rem;
    height: 8rem;
    padding: 0.5rem;

    background: gray;
}

a{
    text-decoration:none ;
    color: snow;
    background: #301675;
    border-radius:5px ;
    border: 1px solid #f2f2f2;
}
</style>

