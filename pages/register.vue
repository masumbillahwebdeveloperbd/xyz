<template>
	<div class="container col-md-6">
		<h2>Register</h2>
		<br>
		<form @submit.prevent="submit">
		  <div class="mb-3">
		    <label class="form-label">Full Name</label>
		    <input v-model.trim="form.name" type="text" class="form-control" placeholder="Write Your Name" autofocus>
		    
		  </div>
		  <div class="mb-3">
		    <label class="form-label">Email address</label>
		    <input v-model.trim="form.email" type="email" class="form-control" placeholder="Write Your Email">
		    
		  </div>
		  <div class="mb-3">
		    <label  class="form-label">Password</label>
		    <input v-model.trim="form.password" type="password" class="form-control" placeholder="Min 6 Character">
		    
		  </div>
		  <button type="submit" class="btn btn-primary">Submit</button>
		</form>
		<br>
		<p>Already Have an account? <nuxt-link to="login">Login</nuxt-link></p>
	</div>
</template>
<script>
	export default{
		
		data(){
			return{
				form:{
					name:'',
					email:'',
					password:''
				}
			}
		},
		methods:{
			submit(){
		
					axios.post('http://www.allessentialbd.com/api/register',this.form)
                     .then(res=>{
                     	console.log(res)
                     	this.$router.push("/dashboard")
                     })
			        
      			
      			}
			}
    }
</script>