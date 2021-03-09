<template>
  <div class="container col-md-6">
    <h2 class="mt-5">Login</h2>
    <br>
    <form @submit.prevent="userLogin">
      <div class="mb-3">
        <label class="form-label">Email address</label>
        <input type="email" v-model.trim="login.email" class="form-control" placeholder="Write Your Email" autofocus>
        
      </div>
      <div class="mb-3">
        <label  class="form-label">Password</label>
        <input type="password" v-model.trim="login.password" class="form-control" placeholder="Min 6 Character">
        
      </div>
      <button type="submit" class="btn btn-primary">Submit</button>
    </form>
    <br>
    <p>Don't Have an account? <nuxt-link to="register">Register</nuxt-link></p>
  </div>
</template>

<script>
export default {
  
  data() {
    return {
      login: {
        email: '',
        password: ''
      }
    }
  },
  methods: {
    userLogin(){
      
        axios.post('http://www.allessentialbd.com/api/login',this.login )
        .then(res=>{
          console.log(res)
          this.$router.push("/dashboard")
        })
        
  
      }
  }
}
</script>