<template>
    <div>
        <div v-for="tareas in tareasList" v-bind:key="tareas.id" >
        <TareasItem v-bind:tarea="tareas" @eliminar-tarea="enviarTarea"/>
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

            }
        }       
              
    }
</script>

<style>
</style>