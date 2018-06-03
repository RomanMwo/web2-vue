<template>
<div id = "app">
 <div id ="beforeLogin" v-if="!isAuthentication">
  <h1> Witaj w systemie zapisu na zajecia !!!</h1>
  <span>Zaloguj sie e-mailem: </span> <input type="email" v-model="email">
  <button @click="toogle()">Wchodze</button>
 </div >
 <div id= "afterLogin" v-else>
   <h1> Witaj w systemie zapisu na zajecia !!!</h1>
   <h2>Witaj {{email}}</h2>
   <button @click="toogle2()">Wyloguj</button>
 </div>
</div>
</template>

<script>
import "milligram";
export default {
name: 'app',
  data() {
    return {
      email: '',
      isAuthentication: false
    }
  },
  methods: {
  toogle() {
    this.isAuthentication = !this.isAuthentication;
    
  },
  toogle2() {
    this.isAuthentication = !this.isAuthentication;
    this.email ="";
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
