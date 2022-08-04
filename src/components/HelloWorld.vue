<template>
<div id="example2">
<div class="container border border-white">
  <div class="row justify-content-md-center">
    <div class="col col-lg-4">
      <form>
  <!-- Email input -->
  <div class="form-outline mb-4 pt-4">
    <label class="form-label" for="username">Email address</label>
    <input type="email" id="username" class="form-control" required  v-model="username"/>
    <div class="text-danger" for="username">{{validateUserName}}</div>

    
  </div>

  <!-- Password input -->
  <div class="form-outline mb-4">
   <label class="form-label" for="password">Password</label>
    <input type="password" id="password" class="form-control" required v-model="password" />
    <div class="text-danger" for="password">{{validatePwd}}</div>
   
  </div>

  <!-- 2 column grid layout for inline styling -->
  <div class="row mb-4">
    <div class="col d-flex justify-content-center">
      <!-- Checkbox -->
      <div class="form-check">
        <input class="form-check-input" type="checkbox" value="" id="form2Example31" checked />
        <label class="form-check-label" for="form2Example31"> Remember me </label>
      </div>
    </div>

    <div class="col">
      <!-- Simple link -->
      <a href="#!">Forgot password?</a>
    </div>
  </div>

  <!-- Submit button -->
  <button type="button" class="btn btn-primary btn-block mb-4" v-on:click="globalHelper">Sign in</button>

  <!-- Register buttons -->
  <div class="text-center">
    <p>Not a member? <a href="#!">Register</a></p>
    <p>or sign up with:</p>
    <button type="button" class="btn btn-link btn-floating mx-1">
      <i class="fab fa-facebook-f"></i>
    </button>

    <button type="button" class="btn btn-link btn-floating mx-1">
      <i class="fab fa-google"></i>
    </button>

    <button type="button" class="btn btn-link btn-floating mx-1">
      <i class="fab fa-twitter"></i>
    </button>

    <button type="button" class="btn btn-link btn-floating mx-1">
      <i class="fab fa-github"></i>
    </button>
  </div>
</form>
    </div>
    
  </div>
</div>
</div>
</template>

<script>
export default {
  data() {
    return {
      username: "",
      password: "",
      validateUserName: "",
      validatePwd: "",
    }
  },
  name: 'HelloWorld',
  methods: {
    globalHelper: function () {
      var email_regex = /^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,4}$/i;
      if(!email_regex.test(this.username))
      {
        this.validateUserName="Invalid email";
         return false;
      }

    this.validateUserName="";
       if(this.password.length<8)
      {
         this.validatePwd="Passsword should be minimum 8 chars";
         return false;
      }
      this.validatePwd="";
      return true;
    }
  }
}



</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
