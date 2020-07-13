<template>
  <div class="section">
    <div class="vista_usuarios">
      <div class="titulo_usuarios">
        <h1><span class="lroja">U</span>suarios</h1>
      </div> 
      <div class="buscador">
        <input type="text" class="" placeholder="Busqueda por nombre de Usuario" v-on:input="getUsuarios" v-model="busquedaUsuario">
      </div>    
      <div v-if="cargado" class="tabla">
        <table>
          <thead>
            <tr>
              <th>ID</th>
              <th>Nombre</th>
              <th>Correo</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="usuario in usuarios" :key="usuario.id" v-on:click="$router.push({name: 'usuario', params: { id: usuario.id}})">
              <td>{{usuario.id}}</td>
              <td>{{usuario.name}}</td>
              <td>{{usuario.email}}</td>          
            </tr>
          </tbody>
        </table>   
      </div>

      <!-- Situaciones -->
        <!-- Cargando Usuarios -->
        <div class="cargando" v-if="!cargado">
          <h4>Cargando Usuarios...</h4>
        </div>        
    </div>   
  </div>
</template>

<script>
  // Librerias
  import axios from "axios";  

  export default {
    name: 'Usuarios',
    data(){
      return {        
        usuarios: null,
        cargado: false,
        busquedaUsuario: ''
      }
    },    
    created(){
      this.getUsuarios();
    },
    methods: {
      getUsuarios(){          
        this.cargado = false;      
        axios.get('https://my-user-manager.herokuapp.com/users')
             .then( res => {               
               if(this.busquedaUsuario === ''){
                this.usuarios = res.data;
               }else{
                this.usuarios = [];                
                res.data.forEach(usu => {
                  let nombre = usu.name.toLowerCase();                  
                  if(nombre.indexOf(this.busquedaUsuario.toLowerCase()) > -1) this.usuarios.push(usu)
                }); 
               }
               this.cargado = true;
             }).catch( error => console.log(error))
      }
    }
  }

</script>

<style>

    .vista_usuarios{
      width: 80%;
      max-width: 1400px;
    } 

    /* Titulo Usuarios */
    .titulo_usuarios{
      margin-bottom: 35px;
    }

    .titulo_usuarios h1{
      text-align: center;
      font-size: 60px;
      font-weight: 500;    
    }
    /* ------   */

    /* Buscador */
    .buscador{
      margin-bottom: 20px;      
    } 

    .buscador input{      
      width: 100%;
    } 
    /* ------   */
   
    /* Tabla */
    .tabla table{      
      border-collapse: collapse;
      width: 100%;
      max-width: 1400px;
      margin: 0 auto;
      text-align: center;
    }

    .tabla th, .tabla td{ 
      padding: 25px; 
      font-size: 20px; 
    }    

    .tabla tr, .tabla td{ 
      transition: .4s ease-in;
    } 

    .tabla thead tr{
      background: rgba(220, 20, 60, .5);
    }

    .tabla tbody tr{
      background: rgba(167, 167, 167, 0.7);
      cursor: pointer;
    }

    .tabla tbody tr:hover:not(#firstrow),tbody tr:hover td:empty{
      background: rgb(255, 104, 104); 
      pointer-events: visible;
    }

    .tabla tbody tr:hover:not(#firstrow){
      transform: scale(1.1);      
      box-shadow: 0px 3px 7px rgba(0, 0, 0, 0.8);
    }
    /* ----- */

    /* Cargando */
    .cargando h4{
      text-align: center;
      font-style: italic;
      font-size: 24px;
    }
    /* ----- */

    @media (max-width: 1200px){    
      /* Titulo Usuarios */
      .titulo_usuarios{
        margin-bottom: 30px;
      }

      .titulo_usuarios h1{
        font-size: 50px;
      }
      /* ------   */
      
      /* Buscador */
      .buscador{
        margin-bottom: 15px;
      } 
      /* ------ */         
    }

    @media (max-width: 725px){
      .vista_usuarios{
        width: 95%;        
      }

      /* Titulo Usuarios */
      .titulo_usuarios{
        margin-bottom: 25px;
      }

      .titulo_usuarios h1{
        font-size: 40px;
      }
      /* ------ */

      /* Buscador */
      .buscador{
        margin-bottom: 10px;
      } 
      /* ------ */ 

      /* Tabla */
      .tabla th, .tabla td{ 
        padding: 15px 2.5px; 
        font-size: 13px; 
      }   
      /* ----- */     
    }
</style>
