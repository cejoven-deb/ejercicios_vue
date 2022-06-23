<script>
export default{
/* data(){   De manera forsosa se tiene que llamar data, ya que esta viene definida dentro de vue.js y 
          con esta se llama archivos de tipo javascrip

   return{

    contador:200,
   };

 },  Data de forma resumida  */
 /* Con los parentesis hago el return y con las llaves invoco el objeto. Al invocarse el objeto se usa : */

data: () =>({contador : 10}), 

/* Los eventos son formas de llamar lógica desde algún componente o algún evento*/
/* La reactividad consiste en que si se mueve todo en el code, en el navegador cambia todo*/
/* Dentro de los methods vamos a ir creando funsiones*/
methods:{
  /* Dentro de los métodos pueden haber varios objetos*/
  saludar(){
    console.log("Hola ")
  },
    incrementar(){
      this.contador++;
    },  
    disminuir(){
      this.contador--;

    },
    resetear(){
      this.contador=10;
    },
},
};

</script>

<template>
<div class="container">
  <h1>Hola desde vue.js3</h1>
  <img src="./assets/logo.svg" alt="logo vue" width="125" height="120">

  <hr />

  <h2>Contador :{{contador}}</h2>
  <button @click="incrementar()">+1</button>
  <button @click="disminuir()">>-1</button>
  <button @click ="resetear()">Reset</button>

  </div>
  
</template>

<style scoped>


.container{

  text-align: center;



}

h1{
font-weight: bolder;


}
h2{
   font-size: 2.5rem;

}

bottom{
cursor: pinter;
font-size: 1.5rem;
margin:0px 6px;



}


</style>

