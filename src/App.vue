<template>
  <div id="app">
    <!--<img src="./assets/logo.png">-->
    <h1>SKILLTREE</h1>
    <br />
    <div id="loginForm">
      <input type="text" name="username" v-model="input.username" placeholder="Username" />
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
        username: "",
        password: ""
      }
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
