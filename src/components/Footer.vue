<template>
  <footer>
    <div class="redes_footer">
      <ul>
        <li><a v-bind:href="links.linkedin"><img src="./../assets/images/redes_sociales/linkedin_logo.png"></a></li>
        <li><a v-bind:href="links.instagram"><img src="./../assets/images/redes_sociales/instagram_logo.png"></a></li>
        <li><a v-bind:href="links.github"><img src="./../assets/images/redes_sociales/github_logo.png"></a></li>
      </ul>
    </div>
    <div class="texto_footer">
      <p>Desarollado por <a class="lroja" v-bind:href="links.personal_web">Jose Antonio Blazquez Cabra</a></p>
    </div>
  </footer>
</template>

<script>
export default {
    name:'Footer',
    data: () => ({
      links: {
        linkedin: "https://www.linkedin.com/in/jose-antonio-blazquez-cabra-2baa25aa/",
        instagram: "https://www.instagram.com/",
        github: "https://github.com/1JoseAntonio1",
        personal_web: "https://joseantoniobc.website/",
      } 
    })
}
</script>

<style>
  footer{
    width: 100%;    
    background: rgb(54, 54, 54); 
    padding: 40px;   
  }  

  /* Reedes */
  .redes_footer ul{
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;  
  }

  .redes_footer ul li {
    position: relative;
    list-style: none;  
  }

  .redes_footer ul li a{
    position: relative;
    width: 60px;    
    height: 60px;
    display: flex;
    justify-content: center;
    align-items: center;
    background: #fff;
    margin: 0 10px;
    text-decoration: none;   
    border-radius: 50%;
    box-shadow: inset -1px -1px 2px rgba(0, 0, 0, 0.2), 2px 2px 5px rgba(0, 0, 0, .8);
    transition: .5s;
  }

  .redes_footer ul li a:hover{
    transform: translateY(-20px);
    box-shadow: inset -1px -1px 2px rgba(0, 0, 0, 0.2), 2px 20px 10px rgba(0, 0, 0, .8)
  }

  .redes_footer ul li a:before{
    content: '';
    position: absolute;
    top: 5px;
    left: 5px;
    right: 5px;
    bottom: 5px;
    border-radius: 50%;
    border: 2px solid rgba(59, 36, 36, .1);
    background: rgb(48, 48, 48);
  }

  .redes_footer ul li a img{
    width: 100%;
    z-index: 1;
  }
  /* ----- */

  /* Texto */
  .texto_footer p{
    color: rgb(240, 240, 240);
    text-align: center;
  }
  /* ----- */

  @media (max-width: 725px){ 
    footer{    
      padding: 20px;   
    }   

    /* Reedes */
    .redes_footer ul li a{      
      width: 45px;    
      height: 45px;
    } 

    .redes_footer ul li a:before{    
      top: 3px;
      left: 3px;
      right: 3px;
      bottom: 3px;    
    }
    /* ------- */

    /* Texto */
    .texto_footer p{
      font-size: 14px;
    }
    /* ----- */
  }
</style>