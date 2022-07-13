<template>
  <div>
    <h1>Formularios</h1>
    
 <img width="100" :src="url" >
 <hr />
 <form @submit.prevent="addUser">
 <div>
  <label >
    Nombre:
     <input  id= "nombre" type="text" placeholder="Nombre " required /> 
  </label>
  </div>
  <div>
   <label >
    Edad:
     <input  id= "nombre" type="number" min="15" max="100" placeholder="Nombre " required /> 
  </label>
  </div>
  <div>
   <label >
    Correo:
     <input  id= "nombre" type="email" placeholder="email@email.com " required /> 
  </label>
  </div>
 <button type="submit">Enviar</button>
 </form>
</div>
</template>
<script>
export default{
  data: ()=>({
    url:"https://cdn.svgporn.com/logos/vue.svg?response-content-disposition=attachment%3Bfilename%3Dvue.svg",

  }),
  methods:{
   
      addUser() {
       console.log("submit")
      },
    },
};
</script>
<style scoped >
div{
  text-align: center;
  margin: 0px 2rem;

}

.contador{
  background: tomato;
  color:snow;
  font-weight: bold;
  height: 400px;

}
</style>