<template>
<div>
<h1> Witaj w systemie zapisu na zajecia !!!</h1>
   <h2>Witaj {{username}}</h2>
   <button @click="out()">{{buttonLabelToDisplay}}</button>
  </div>
</template>

<script>
export default {
  props: ['buttonLabel2'],
  props: ['username'],
 data() {
     return {
         empty: ''
     }
 },
 methods: {
     out() {
         this.$emit('logout', '');
     }
 },
 computed: {
  buttonLabelToDisplay() {
    return this.buttonLabel2 || 'Wyloguj sie';  
  }
 }
}
</script>