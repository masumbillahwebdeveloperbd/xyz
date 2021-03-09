<template>
	<nav class="navbar navbar-expand-lg navbar-light bg-light mb-5">
  <div class="container-fluid">
  	<nuxt-link class="navbar-brand" to="/">MyPage</nuxt-link>
    
  <!--   <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button> -->
    <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
      <div class="navbar-nav">
        <nuxt-link class="nav-link" to="/">Home</nuxt-link>
        
      </div>
      <div class="navbar-nav">
        <nuxt-link class="nav-link" to="/dashboard">Dashboard</nuxt-link>
      </div>
      
      <template >
        <div class="navbar-nav ml-auto">
        <nuxt-link class="nav-link" to="/login">Login</nuxt-link>
        <nuxt-link class="nav-link" to="/register">Register</nuxt-link>
      </div>
      </template>
      <template>
        <div class="navbar-nav ml-auto">
        
        <a @click.prevent="logout" class="nav-link" to="/login">Logout</a>
      </div>
      </template>
      

      
   
   
    </div>
  </div>
</nav>
</template>
<script>
export default{
    name:"Navbar",
    methods:{
    logout(){
      this.$router.push('/login')
    }
  }
}
</script>