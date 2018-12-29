<template>
  <div id="app">
    <!--<img src="./assets/logo.png">-->
    <h1>SKILLTREE</h1>
    <br />
    <div id="loginForm">
      <input type="email" name="username" v-model="input.email" placeholder="Email" />
      <br />
      <br />
      <input type="password" name="password" v-model="input.password" placeholder="Password" />
      <br />
      <button type="button" v-on:click="login()">Login</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      input: {
        email: "",
        password: ""
      }
    }
  },
  methods: {
    login(){
      if(validateLoginForm()){
        this.$http.post('http://skillt.coredumped.es/login', input).then(okResponse => {
          //TODO: Go to main webpage
        }, errorResponse => {
          //TODO: Display error, login is bad
        })
      }
    },
    validateLoginForm(){
      return this.validateEmail(this.input.email) && this.validatePassword(this.input.password)
    },
    validateEmail(email) {
      var re = /\S+@\S+\.\S+/;
      return re.test(email);
    },
    validatePassword(password) {
      return password.length > 8
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

#loginForm {
  background-color: aquamarine;
  padding-top: 20px;
  padding-bottom: 20px;
  margin-right: 100px;
  margin-left: 100px;
}

h1, h2 {
  font-weight: normal;
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
