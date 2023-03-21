<template>
    <div class="menu">
      <!-- Aqui você pode adicionar os links do menu -->
      <router-link to="/">Home</router-link>
      <router-link to="/stats">Stats</router-link>
      <router-link to="/config">Config</router-link>
    </div>
  </template>
  
  <script>
  export default {
    name: "Menu",
  };
  </script>
  
  <style scoped>
  .menu {
    /* Adicione o estilo do seu menu aqui */
  }
  </style>