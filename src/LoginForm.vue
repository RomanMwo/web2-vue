<template>
   <div>
    <h1> Witaj w systemie zapisu na zajecia !!!</h1>
       <label>Zaloguj si� e-mailem</label>
       <input type="email" v-model="email">
       <button @click="enter()">{{buttonLabelToDisplay}}</button>
   </div>
</template>

<script>
export default {
  props: ['buttonLabel'],
 data() {
     return {
         email: ''
     }
 },
 methods: {
     enter() {
         this.$emit('login', this.email);
     }
 },
 computed: {
  buttonLabelToDisplay() {
    return this.buttonLabel || 'Zaloguj sie';  
  }
}
}
</script>