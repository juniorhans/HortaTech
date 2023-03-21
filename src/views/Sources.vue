<template>
    <div class="main">
        <Header :Title="title"/>
        <div class="center">
        <p><b>FONTES</b> <br>
            <b>Sistema de Banco de dados.</b> Acessado em: https://firebase.google.com/ <br>
            <b>FrameWork para o desenvolvimento das telas.</b>Acessado em: https://vuejs.org <br>
            <b>Base da linguagem para o desenvolvimento das telas.</b> Acessado em: https://www.javascript.com <br>
            <b>Projeto Escola Verde. </b>Acessado em: https://escolaverde.org/site/ <br>
        </p>
    </div> 

    </div>


    
</template>

<script>
import Header from "../components/Header.vue"

export default {
    data(){
        return{
            title:"Fontes"
        }
    },
    components:{
    Header}
    

}
</script>

<style>

    
</style>