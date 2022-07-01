<template>
    <div id="add-container">
        <form @submit.prevent="addTarea">
            <label id="label-tarea">Nueva Tarea:</label>        
            <input type="text" v-model="title">
        </form>


    </div>
</template>
<script>
//import { uuid } from "uuid";
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
            // console.log(newTarea)

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
    width: 100%;
}
</style>