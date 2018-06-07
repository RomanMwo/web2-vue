<template>
<div id = "app">
 <div id ="beforeLogin" v-if="!isAuthentication">
  <login-form @login="toogle($event)" ></login-form>
 </div >
 <div id= "afterLogin" v-else>
   <login-out :username="loginfo" @logout="toogle($event)" ></login-out>
   <meeting-page :username="loginfo"></meeting-page>
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
 
}
#outbutton{
display: inline;
position: absolute;
    left: 80%;
    top: 15%;
}
h1 {
  font-weight: normal;
  color: red;
}
.info{
color: green;
}
#emptyState{
color: red;
}
</style>
