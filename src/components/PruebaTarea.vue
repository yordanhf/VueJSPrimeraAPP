<template>
    <div id="search-container">
        <label id="label-btarea">Buscar Tarea: </label>
        <input type="text" v-model="title" @input ="sendText">
    </div>
</template>

<script>
export default{
    name:"PruebaTarea",    
    data(){
        return{
            title:''
        }
    },
    methods:{
        sendText(){
            this.$emit('envia-texto',this.title)
        }
    }   

}
</script>

<style scoped>
#search-container{

    padding: 10px;
    width: 100%;    
    display: flex;
    justify-content: center;
    align-items: center;
}
#label-btarea{
   
   font-size: 0.9em;

}
input{
    margin: 10px;
    padding: 10px;
    outline: none;
    border: solid 1px #ccc;
    width: 50%;
    border-radius: 4px;
}
button{
    margin: 10px;
    border: none;
    border-radius: 3px;
    padding: 10px;
    background-color: #ccc;
    color: black;    
}

button:hover{
    background-color: darkblue;
    color: rgb(250, 245, 245);
}


</style>