<template>
    <div id="add-container">
        <form @submit.prevent="addTarea">
            <label id="label-tarea">Nueva Tarea:</label>
            <br>            
            <input type="text" v-model="title">
            <button id="binsertar" @click.prevent="addTarea">Insertar </button>
        </form>
    </div>
</template>

<script>
export default{
    name:"TareasAdd",
    data(){
        return {
            title: ''
        }
    },
    methods:{
        addTarea(){  
            const newTarea = {
                id: this.randomKey(),
                title: this.title,
                completed: false
            }; 
           
            this.title = '';            
            this.$emit('add-tarea', newTarea)            

        },
         randomKey() {
            return (new Date()).getTime() + Math.floor(Math.random() * 10000).toString()
            } 
            }
}
</script>

<style scoped>
#add-container{
    padding: 10px;
}
#label-tarea{
   color: darkblue;
}
input{
    padding: 10px;
    outline: none;
    border: solid 1px #ccc;
    width: 85%;
}
#binsertar{
    margin: 10px;
    border: none;
    border-radius: 3px;
    padding: 10px;
    background-color: #ccc;
    color: black;
}

#binsertar:hover{
    background-color: #020b81;
    color: white;

}
</style>