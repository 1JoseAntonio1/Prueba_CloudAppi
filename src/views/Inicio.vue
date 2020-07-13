<template>
  <div class="section">
    <div class="presentacion">  
      <div>
        <div class="titulo">
          <h1><span class="lroja">C</span>loud<span class="lroja">A</span>ppi</h1>
        </div>    
        <div class="info">
          <h2>Prueba de acceso</h2>
          <p>Desarrollada por Jose Antonio Blazquez Cabra con el framework <a href="https://vuejs.org/" class="lroja">Vue.js</a></p> 
        </div>
      </div>
      <div>
        <div class="btn">
          <router-link :to="{name: 'usuarios'}">
            <span></span>
            <span></span>
            <span></span>
            <span></span>
            Ir a Ver
          </router-link>
        </div>
      </div> 
      <div>
        <div class="frase">
          <p>“Confía en tu talento, tú puedes”</p>
        </div>
      </div>                
    </div>
  </div>
</template>

<script>
export default {
  name: 'Inicio',
  data () {
    return {
      
    }
  }
}
</script>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Open+Sans:ital@1&display=swap');
    @import url('https://fonts.googleapis.com/css2?family=Dancing+Script&display=swap');

    .presentacion{      
      padding: 20px 10px;
      height: 80%;
      width: 95%;

      max-width: 1400px;
      max-height: 800px;

      display: flex;
      flex-direction: column; 
      justify-content: space-between;     
      align-content: flex-start;
    }    

    /* Titulo */
    .presentacion .titulo{      
      margin-bottom: 80px;      
    }

    .presentacion .titulo h1{
      text-align: center;      
      font-size: 65px;
      font-weight: 500;      
    }
    /* ------ */

    /* Info */
    .presentacion .info{      
      padding: 0 20px;
    }

    .presentacion .info h2{ 
      font-size: 35px; 
      font-weight: 400;     
    }

    .presentacion .info p{  
      font-size: 20px; 
      margin: 0;
      font-family: 'Open Sans', sans-serif;
    }
    /* ------ */

    /* Boton */
    .presentacion .btn {
      position: relative;
      display: flex;
      justify-content: center;
      align-items: center;      
    }

    .presentacion .btn a{            
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      background:  rgb(31, 31, 31);
      color: rgb(231, 231, 231);
      font-size: 20px;
      padding: 15px 35px;
      letter-spacing: 1.5px;      
      box-shadow: 0 20px 50px rgba(0,0,0,.5);
      overflow: hidden;
      text-decoration: none;
    }

    .presentacion .btn a:hover{            
      background: rgb(0, 0, 0);
      color: rgb(255, 255, 255);          
      box-shadow: 0 20px 50px rgba(0, 0, 0, 0.8);      
    }

    .presentacion .btn a:hover:before{            
      background: rgba(255, 255, 255, 0.1);     
    }

    .presentacion .btn a:before{
      position: absolute;
      content: '';
      top: 3px;
      left: 3px;
      bottom: 3px;
      width: 50%;
      background: rgba(255, 255, 255, 0.1);
    }

    .presentacion .btn a span:nth-child(1){
      position: absolute;      
      top: 0;
      left: 0;      
      width: 100%;
      height: 3px;      
      background: linear-gradient(to right, rgb(31, 31, 31), crimson);
      animation: animacion1 1.5s linear infinite;
    }

    .presentacion .btn a:hover span:nth-child(1){
      background: linear-gradient(to right, rgb(0, 0, 0), crimson);
      animation: animacion1 1s linear infinite;
    } 

    .presentacion .btn a span:nth-child(2){
      position: absolute;      
      top: 0;
      right: 0;      
      width: 3px;
      height: 100%;      
      background: linear-gradient(to bottom, rgb(31, 31, 31), crimson);
      animation: animacion2 1.5s linear infinite;
      animation-delay: .75s;
    }

    .presentacion .btn a:hover span:nth-child(2){
      background: linear-gradient(to bottom, rgb(0, 0, 0), crimson);
      animation: animacion2 1s linear infinite;
      animation-delay: .5s;
    } 

    .presentacion .btn a span:nth-child(3){
      position: absolute;      
      bottom: 0;
      left: 0;      
      width: 100%;
      height: 3px;        
      background: linear-gradient(to left, rgb(31, 31, 31), crimson);
      animation: animacion3 1.5s linear infinite;      
    }

    .presentacion .btn a:hover span:nth-child(3){
      background: linear-gradient(to left, rgb(0, 0, 0), crimson);
      animation: animacion3 1s linear infinite;
    } 

    .presentacion .btn a span:nth-child(4){
      position: absolute;      
      top: 0;
      left: 0;      
      width: 3px;
      height: 100%;    
      background: linear-gradient(to top, rgb(31, 31, 31), crimson);
      animation: animacion4 1.5s linear infinite;
      animation-delay: 0.75s;
    }

    .presentacion .btn a:hover span:nth-child(4){
      background: linear-gradient(to top, rgb(0, 0, 0), crimson);
      animation: animacion4 1s linear infinite;
      animation-delay: 0.5s;
    }
    
    /* ------ */

    /* Frase */
    .presentacion .frase p{
      float: right;
      max-width: 300px;
      width: 45%; 
      text-align: center;         
      margin: 0;    

      font-family: 'Dancing Script', cursive; 
      font-size: 20px; 
    }    
    /* ------ */

    @media (max-width: 1200px){
      /* Titulo */
      .presentacion .titulo{      
        margin-bottom: 50px;
      }

      .presentacion .titulo h1{        
        font-size: 55px;      
      }
      /* ------ */

      /* Info */
      .presentacion .info{      
        padding: 0 15px;
      }

      .presentacion .info h2{ 
        font-size: 32px;           
      }

      .presentacion .info p{  
        font-size: 17px; 
        
      }
      /* ------ */ 

      /* Boton */
      .presentacion .btn a{      
        font-size: 18px;             
      }
      /* ------ */

      /* Frase */
      .presentacion .frase p{        
        width: 35%;
        font-size: 17px; 
      }    
      /* ------ */  
    }

    @media (max-width: 725px){
      /* Titulo */
      .presentacion .titulo{      
        margin-bottom: 35px;
      }

      .presentacion .titulo h1{        
        font-size: 43px;        
      }
      /* ------ */

      /* Info */
        .presentacion .info{      
          padding: 0;
        }

        .presentacion .info h2{ 
          font-size: 24px;           
        }

        .presentacion .info p{  
          font-size: 14px; 
          
        }
      /* ------ */ 

      /* Boton */
      .presentacion .btn a{      
        font-size: 17px;  
        padding: 10px 30px;           
      }
      /* ------ */

      /* Frase */
      .presentacion .frase p{        
        width: 40%;
        font-size: 15px; 
      }    
      /* ------ */  
    }

    /* Animaciones */
    @keyframes animacion1{
      0%{
        transform: translateX(-100%);
      }100%{
        transform: translateX(100%);
      }
    }

    @keyframes animacion2{
      0%{
        transform: translateY(-100%);
      }100%{
        transform: translateY(100%);
      }
    }

    @keyframes animacion3{
      0%{
        transform: translateX(100%);
      }100%{
        transform: translateX(-100%);
      }
    }

    @keyframes animacion4{
      0%{
        transform: translateY(100%);
      }100%{
        transform: translateY(-100%);
      }
    }
    /* ------ */ 
</style>