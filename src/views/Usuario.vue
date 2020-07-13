<template>
  <div class="section">
    <div v-if="cargado" class="titulo_usuario">
      <div class="titu_usu">
        <h1><span class="lroja">U</span>suario</h1>
      </div>      
      <div class="datos_usuario">
        <img src="./../assets/images/usuario.png">
        <div>         
          <p><i>ID:</i> {{usuario.id}}</p>
          <p><i>Nombre:</i> {{usuario.name}}</p>
          <p><i>Correo:</i> {{usuario.email}}</p>
        </div>
      </div>
      <div class="btn_volver">
        <router-link class="lroja" :to="{name: 'usuarios'}">
          Volver
        </router-link>
      </div>     
    </div> 

    <!-- Cargando Usuarios -->
    <div class="cargando" v-if="!cargado">
      <h4>Cargando Usuario...</h4>
    </div>    
  </div>
</template>

<script>
  // Librerias
  import axios from "axios";

  export default {
    name: 'Usuario',
    data(){
      return {
        usuario: null,
        cargado: false,
        error: false        
      }
    },    
    created(){
      this.getUsuario();
    },
    methods: {
      getUsuario(){       
        let url_usuario= "https://my-user-manager.herokuapp.com/users/" + this.$route.params.id;
        axios.get(url_usuario)
             .then( res => {                
                this.usuario = res.data;              
                this.cargado = true;
             }).catch( error => {
               console.log(error);
               this.error = true;
             })
      }
    }
  }

</script>

<style>

  /* Titulo Usuario */
  .titu_usu h1{
    text-align: center;
    font-size: 55px;
    font-weight: 500;    
  }
  /* ------   */

  .titulo_usuario{
    width: 70%;
    max-width: 1200px;    

    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
  }

  .titulo_usuario .datos_usuario{    
    width: 100%;

    display: flex;    
    align-items: center;    
  }

  .titulo_usuario .datos_usuario div{    
   padding: 25px;  
  }

  .titulo_usuario .datos_usuario div p{    
   margin: 0; 
   font-size: 27px;  
  }

  .titulo_usuario .datos_usuario div{   
    width: 50%;           
  }

  .titulo_usuario img{    
    width: 50%;    
  }

  /* Boton Volver */
  .btn_volver a{ 
    background: rgba(0, 0, 0, 0.5);   
    padding: 12px 25px;
    width: 100px;
    border-radius: 20px;
    border: 2px solid rgba(220, 20, 60, 0.61);
    text-decoration: none;
  }

  .btn_volver a:hover{ 
    background: rgb(0, 0, 0);  
    border: 2px solid rgb(220, 20, 60);
    color: crimson;
  }
  /* ------ */

    @media (max-width: 1200px){    
      /* Titulo Usuario */
      .titu_usu h1{
        font-size: 50px;
      }
      /* ------   */
      
      .titulo_usuario{
        width: 90%;        
      }     

      .titulo_usuario .datos_usuario div p{       
        font-size: 20px; 
      }     
    }

    @media (max-width: 725px){
      /* Titulo Usuario */
      .titu_usu h1{
        font-size: 40px;
      }
      /* ------   */

      .titulo_usuario{
        width: 95%;        
      }

      .titulo_usuario .datos_usuario{
        justify-content: center; 
        flex-direction: column; 
      }

      .titulo_usuario .datos_usuario div{
        width: 95%;
      }

      .titulo_usuario .datos_usuario div{    
        padding: 18px;  
      }

      .titulo_usuario .datos_usuario div p{       
        font-size: 17px; 
      } 

      .titulo_usuario img{    
        width: 80%;        
      }    
    }
</style>
