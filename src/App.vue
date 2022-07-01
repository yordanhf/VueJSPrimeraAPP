<template>
 <div>
  <div id="header"></div>
  <div id="main-container">
    <h2>
      Tareas:
    </h2>
    <TareasComp v-bind:tareasList="copyTareas" 
    @eliminar-tarea="borrarTarea"
    @cambiar-tarea="cambiaTarea" />
  </div>
 </div>
</template>

<script>
//import SearchItem from './components/SearchItem.vue'
//import TareasAdd from './components/TareasAdd.vue'
import TareasComp from './components/TareasComp.vue'

export default {
  name: 'App',
  components: {  
      TareasComp 
  },
  methods:{
    borrarTarea(id){
      this.tareas = this.tareas.filter(tarea => tarea.id != id );
      this.copyTareas = [... this.tareas];      
    },
    cambiaTarea(id){
      console.log(id)
    }

  },
  data(){
    return {
      tareas: [
        {
          id: 0,
          title: "Comprar la Comida",
          completed: false
        },
        {
          id: 1,
          title: "Sacar al perro",
          completed: true
        },
        {
          id: 2,
          title: "Jugar Playstation",
          completed: false
        },
          {
          id: 3,
          title: "Terminal Sitio en Vue",
          completed: true
        }
      ],
      copyTareas: []
    }
  },
  created(){
    this.copyTareas = [... this.tareas];    
  }
}
</script>

<style>
*{
  box-sizing: border-box;  
}

body{
  font-family: Geneva, Tahoma, sans-serif;
  font-size: 1.5em;
  padding: 0;
  margin: 0;
}

#main-container{
  border: solid 1px #ccc;
  width: 600px;
  margin: 100px auto;
}

#header{
  background: rgb(8, 6, 146);
  padding: 10px;
  width: 100%;
}

h2{
  padding: 0 10px;
}
</style>
