<template>
    <div class="header-Main">
      <button class="menu-btn">
        Menu
        <div class="menu-container">
          <button @click="gotoApresentation()">
            <i class="fa-solid fa-person-chalkboard"></i> <br>Apresentação
          </button>
          <button @click="gotoCatalogSheet()">
            <i class="fa-solid fa-clipboard"></i> Ficha <br>Catalográfica
          </button>
          <button @click="gotoSource()">
            <i class="fa-solid fa-magnifying-glass"></i> <br>Fontes
          </button>
          <img src="../../public/imgs/PEV-aprovado-pelo-MEC.png" width="50" height="50">
        </div>
      </button>
      <p class="header-Title">{{Title}}</p>
     
      <button class="back-button" @click="goBack()">SAIR</button>
    </div>
  </template>
  
  <script>
  export default {
    name:"Header",
    data(){
      return{}
    },
    methods: {
      goBack(){
        this.$router.push('/')
      },
      gotoApresentation(){
        this.$router.push('/apresentation')
      },
      gotoCatalogSheet(){
        this.$router.push('/catalog')
      },
      gotoSource(){
        this.$router.push('/sources')
      }
    },
    props:['Title']  
  }
  </script>
  
  <style scoped>
  .menu-container{
    display: flex;
    flex-direction: row;
    margin-left: 0px;
    position: absolute;
    top: 100%;
    left: 0;
    display: none;
  }
  .menu-btn:hover .menu-container{
    display: flex;
    flex-direction: column;
    background-color: #064B15;
    border-radius: 0px 0px 40px 40px; 
    padding: 0.5rem;
  }
  .menu-btn{
    background-color: transparent;
    border: none;
    color: #fff;
    position: relative;
  }
  .menu-btn:focus .menu-container{
    display: flex;
    flex-direction: column;
    background-color: #064B15;
    border-radius: 0px 0px 40px 40px; 
    padding: 0.5rem;
  }
  .header-Main{
    background-color: #064B15;
    width: 100vw;
    height: 20vh;
    margin-top: 0;
    display: flex;
    justify-content: flex-start;
    align-items: center;
    padding: 0;
  }
  
  .header-Title{
    font-size: 8vh;
    color: #fff;
    margin:20rem;
  }
  
  .back-button{
    background-color: #fff;
    display: flex;
    padding: 1px;
    justify-content: center;
    align-items: center;
    color: #064B15;
    margin-left: 75vw;
    font-size: 3rem;
    border-radius: 40px;
    position: absolute;
  }
  
  @media screen and (max-width: 600px) {
    .header-Main{
      background-color: #064B15;
      width: 100vw;
      height: 15vh;
      /* border-radius: 0px 0px 40px 40px;  */
    }
    .header-Title{
      font-size: 4vh;
      margin:2rem;
    }
    .back-button{
      display: flex;
      padding: 1rem;
      margin-left: 75vw;
      font-size: 1rem;
      border-radius: 40px;
    }
  }
  </style>
  