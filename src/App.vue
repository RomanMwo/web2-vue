<template>
<div id = "app">
 <div id ="beforeLogin" v-if="!isAuthentication">
  <login-form @login="toogle($event)" ></login-form>
 </div >
 <div id= "afterLogin" v-else>
   <login-out :username="loginfo" @logout="toogle($event)" ></login-out>
   <meeting-page></meeting-page>
 </div>
</div>
</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";
import LoginOut from "./LoginOut";
import MeetingPage from "./MeetingPage";
export default {
name: 'app',
components: {LoginForm, LoginOut, MeetingPage},
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
h1 {
  font-weight: normal;
  color: red;
}
.info{
color: green;
}
</style>
