<template>
 <form @submit.prevent="procesarFormulario">
  <!-- v-model="text" -->
  <input 
  type="text"
  class="form-control my-2"
  placeholder="Ingrese Nombre"
  v-model.trim="tarea.nombre">
<!-- v-model="checkbox" -->
  <div class="form-check form-check-inline">
    <input 
    type="checkbox"
    id="check-1"
    class="form-check-input"
    v-model="tarea.categorias"
    value="javascript">
    <label for="check-1" class="form-check-label"> JavaScript</label>
  </div>
  <div class="form-check form-check-inline">
    <input 
    type="checkbox"
    id="check-2"
    class="form-check-input"
    v-model="tarea.categorias"
    value="nodejs">
    <label for="check-2" class="form-check-label"> Node.js</label>
  </div>
<!-- v-model="radio" -->
  <div class="mt-2">
    <div class="form-check form-check-inline">
      <input 
      type="radio"
      id="radio-1"
      class="form-check-input"
      v-model="tarea.estado"
      value="urgente">
      <label for="radio-1" class="form-check-label"> Urgente</label>
    </div>  
    <div class="form-check form-check-inline">
      <input 
      type="radio"
      id="radio-2"
      class="form-check-input"
      v-model="tarea.estado"
      value="relax">
      <label for="radio-2" class="form-check-label"> Relax</label>
    </div> 
  </div>
<!-- v-model="number" -->
  <div class="mt-2">
    <input type="number"
    class="form-control"
    v-model.number="tarea.numero">
  </div>
  <button 
    class="btn btn-dark mt-2 btn-block" 
    type="submit"
    :disabled="bloquear">Procesar</button>
 </form>
 <hr>
 <p>{{ tarea }}</p>
</template>

<script>


export default {
  name: 'HomeView',
  components: {
    
  },
  data() {
    return {
      tarea: {
        nombre: '',
        categorias: [],
        estado: '',
        numero: 0
      }
    }
  },
  methods: {
  procesarFormulario(){
    if(this.tarea.nombre.trim() === ''){
      console.log('nombre Vacío')
      return
    }
      console.log('no está vacío')
      //se envían los datos

      this.tarea = {
        nombre: '',
        categorias: [],
        estado: '',
        numero: 0
      }
    }
  },
  computed:{
      bloquear(){
        return this.tarea.nombre.trim() === '' ? true : false
      }
  },
}
</script>
