<template>
  <div id="app">
    <!--NavBar-->
    <NavBar/>

    <!--Contenido de la pagina-->
    <router-view/>    

    <!--Footer-->
    <Footer/>
  </div>
</template>

<script>

  // Componentes
  import NavBar from '@/components/NavBar'
  import Footer from '@/components/Footer'
  
  export default {
    name: 'App',
    data () {
      return {

      }
    },
    components:{
      NavBar,Footer
    }
  }
</script>

<style>
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  html, body{       
    overflow-x: hidden;
    background: linear-gradient(to bottom,rgba(0, 0, 0, .3),rgba(0, 0, 0, .3),rgba(0, 0, 0, .3),rgba(0, 0, 0, .3),rgba(0, 0, 0, .3), rgba(0, 0, 0, .3), rgba(0, 0, 0, .5), rgba(0, 0, 0, .7), rgba(0, 0, 0, .9)), url("./assets/images/background1.jpg") center no-repeat;
    background-size: cover;
    background-attachment: fixed; 
  }

  .section{      
      width: 100%;
      height: 90vh; 
      color: rgb(240, 240, 240);          

      display: flex;
      justify-content: center;
      align-items: center;
    }

  .lroja{
    color: crimson;
  }  
</style>

