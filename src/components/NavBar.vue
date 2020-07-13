<template>
  <nav>
    <b-navbar toggleable="lg" type="dark" variant="dark">
        <b-navbar-brand :to="{name: 'inicio'}"><span class="lroja">J</span>OSE <span class="lroja">A</span>NTONIO <span class="lroja">BC</span></b-navbar-brand>

        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

        <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav class="ml-auto">
            <b-nav-item :to="{name: 'inicio'}" active-class="active" exact>Inicio</b-nav-item>
            <b-nav-item :to="{name: 'usuarios'}" active-class="active" exact>Usuarios</b-nav-item>
        </b-navbar-nav>      
        </b-collapse>
    </b-navbar>
  </nav>
</template>


<script>
export default {
  name: 'NavBar',
  data () {
    return {
      
    }
  }
}
</script>

<style>
    
</style>