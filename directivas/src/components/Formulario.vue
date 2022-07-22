/*Se hace por esta parte un script*/
<script>
export default {
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
      const proyecto = {
        proyectos: this.proyecto,
        tipo: this.tipo,
        urgente: this.urgente,
      };
      this.proyectos.push(proyecto);
      this.proyecto = "";
      this.tipo = "";
      this.urgente = false;
   
    },
  },
  computed:{ /*Declaramos la función para que me contabilice los proyectos de 
               manera automática*/
    numeroProyectos(){
        return this.proyectos.length
    }

  },
};
</script>

<template>
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
  <hr />
  <h3>
    Total Proyectos:{{numeroProyectos}}
  </h3>
  <div class="table-responsive">
    <table class="table table-dark">
      <thead>
        <tr>
         <th>#</th> 
         <th>Proyecto</th> 
         <th>Tipo</th> 
         <th>Urgente</th> 
        </tr>
      </thead>
      <tbody>
        <tr v-for="(proyecto, index) in proyectos"  :key="index">
          <td>{{index + 1}}</td>
          <td>{{proyecto.proyecto}}</td>
          <td>{{proyecto.tipo}}</td>
          <td :class="proyecto.urgente ? 'bg-success':'bg-danger' ">
          {{proyecto.urgente ? "SI" : "NO"}}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
