<template>
    <div>
        <div v-for="tareas in tareasList" v-bind:key="tareas.id" >
        <TareasItem v-bind:tarea="tareas" 
        @eliminar-tarea="enviarTarea"
        @cambiar-tarea="enviarId"/>
        </div>
    </div>
</template>

<script>
    import TareasItem from "./TareasItem"

    export default{
        name: "TareasComp",
        props: ["tareasList"],
        components: {TareasItem},
        methods:{
            enviarTarea(id){
                this.$emit('eliminar-tarea', id)
            },
            enviarId(id){
                this.$emit('cambiar-tarea', id)
              

            }
        }       
              
    }
</script>

<style>
</style>