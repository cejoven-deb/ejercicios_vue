
<template>
 

  <div class ="row">
    <div class="col-12 mb-4">
   <progress-bar :porcentaje="porcentaje"/>
    </div>


    <div class= "col-12 col-md-4">

       <form @submit.prevent="RegistrarProyecto">
    <div class="mb-3">
      <label class="form-label">Proyecto</label>
      <input
        v-model.trim="proyecto"
        type="text"
        class="form-control"
        required
      />
    </div>

    <div class="mb-3">
      <label class="form-label">Actividad</label>
      <select v-model.trim="tipo" class="form-selelct" required>
        <option disabled selected value="">Seleccione un tipo...</option>
        <option value="1">Aplicación Web con Vue.js</option>
        <option value="2">Backend Service con Node.js</option>
        <option value="3">App Móvil con React Native</option>
      </select>
    </div>

    <div class="mb-3">
      <label for="exampleInputPassword1" class="form-check-label"
        >Urgente</label>
      <input v-model.trim="urgente" type="checkbox" class="form-check-input" />
    </div>

    <button type="submit" class="btn btn-primary">Guardar</button>
  </form>
    </div>

    <div class = "col-12 col-md-8"> 
    <total-proyectos
    :numeroProyectos="numeroProyectos" 
    :proyectos="proyectos"
    :cambiarEstado="cambiarEstado"
    :limpiarData="limpiarData"/>

    </div>

  </div>
</template>


/*Se hace por esta parte un script*/
<script>
import ProgressBar from './ProgressBar.vue';
import TotalProyectos from './TotalProyectos.vue';
export default {
  components:{ProgressBar, TotalProyectos},
  
  data: () => ({
    /*Para esta parte se ennumeran los formularios*/
    Proyecto: "",
    tipo: "",
    urgente: false, /* se lo deja de esta manera porque solo recibe dos valores*/
    proyectos:[], /*Se define como una propiedad extra, se define como un arreglo vacío*/
   
  }),
  /*En esta parte se pueden definir los métodos que en si son funciones*/

  methods: {
    RegistrarProyecto() {

      // Completado : False

      const proyecto = {
        proyectos: this.proyecto,
        tipo: this.tipo,
        urgente: this.urgente,
        completado:false,
      };

      this.proyectos.push(proyecto);
    
      this.saveData();
      this.proyecto = "";
      this.tipo = "";
      this.urgente = false;
    },
    
   
  
    cambiarEstado(proyecto,campo){
      //this.proyectos[id].urgente = !this.proyectos[id].urgente ;
      proyecto[campo]= !proyecto[campo];
      this.saveData();
      
    },

    saveData(){
     localStorage.getItem("proyectos", JSON.stringify(this.proyectos) );
    },
    limpiarData(){
    this.proyectos=[],
    localStorage.clear();
   },
  },
    computed:{ /*Declaramos la función para que me contabilice los proyectos de 
               manera automática*/
    numeroProyectos(){
        return this.proyectos.length;
    },
    porcentaje(){
      let completados = 0 ;
      this.proyectos.map(proyecto =>{
        if(proyecto.completado){
          completados++;

        }

      });

     return completados*100/this.numeroProyectos || 0;
    },

  },

   mounted()
  {
    /*En esta parte vamos a trabajar en todo lo referente al localstorage*/
  this.proyectos = JSON.parse( localStorage.getItem("proyectos")) || [];

  },
  
  

};

</script>

