<template>
<div id = "app">
 <div id ="beforeLogin" v-if="!isAuthentication">
  <login-form @login="toogle($event)" ></login-form>
 </div >
 <div id= "afterLogin" v-else>
   <login-out :username="loginfo" @logout="toogle($event)" ></login-out>
 </div>
</div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";
import LoginOut from "./LoginOut";
export default {
name: 'app',
components: {LoginForm, LoginOut},
  data() {
    return {
      email: '',
      isAuthentication: false,
      loginfo: ''
    }
  },
  methods: {
  toogle(mail) {
    this.isAuthentication = !this.isAuthentication;
    this.email=mail;
    this.loginfo = mail;
    
  }
 }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1, h2 {
  font-weight: normal;
  color: red;
}
</style>
