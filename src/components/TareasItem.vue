<template>
    <div class="tarea" v-bind:class="{completed: tarea.completed}">
        <div class="tarea-body" v-bind:class="{completed: tarea.completed}">
            <input type="checkbox" 
            :checked="tarea.completed"             
            @change="$emit('cambiar-tarea', tarea.id)" >
            {{tarea.title}}
        </div>
        <div class="tarea-action">
            <button @click="$emit('eliminar-tarea', tarea.id)">Eliminar</button>
        </div>
    </div>
</template>

<script>
export default{
    name: "TareasItem",
    props: ["tarea"]
    
    
    }
</script>

<style scoped>

.tarea{
    border-bottom: solid 1px #ccc;
    padding: 10px;
}

.tarea:not(.completed):hover{
    background-color: #eee;
}

.completed{
    color: #ccc;
    text-decoration: line-through;
}

.completed .tarea-body{
    text-decoration: line-through;
}

.tarea-body, .tarea-action{
    display: inline-block;
    vertical-align: top;
}

.tarea-body {
    width: 85%;
}

.tarea-action{
    padding: 0 10px;
    width: 10%;
}

button{
    border: none;
    border-radius: 3px;
    padding: 10px;
    background-color: #ccc;
    color: black;    
}

button:hover{
    background-color: #da2020;
    color: white;
}
</style>