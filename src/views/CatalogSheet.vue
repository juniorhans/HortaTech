<template>
  <div class="main">
      <Header :Title="title"/>
          <div class="center">
          <p><b>HortaTech</b> <br>
            Pensando em automação de irrigação?<br> 
      realizando automação de um sistema de irrigação por 
      gotejamento<br> através de sensores e monitorando de forma remota e em tempo real<br>
      <br><b>ISBN</b> 978-65-00-64412-8 <br><br><b>Autores:</b> Ramon Barros Gomes<br> Elpídio Hans dos Santos leão Júnior<br>
      Pedro Henrique Ferreira Amorim da Silva<br> Victor Augusto Medeiros Balbino<br> 
      Adão Thalisson Castro Guimarães<br> Manoel Ferreira de Santana Filho
  </p>
        
          
          </div> 
  </div>

  

</template>

<script>
import Header from "../components/Header.vue"

export default {
  data(){
      return{
          title:"Ficha Catalográfica"
      }
  },
  components:{
  Header}
  

}
</script>

<style>
  .center {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
</style>




