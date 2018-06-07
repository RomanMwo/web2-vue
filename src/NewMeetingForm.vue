<template>
    <form @submit.prevent="addNewMeeting()">
            <h3>Dodaj nowe spotkanie</h3>
            <label>Nazwa</label>
            <input type="text" v-model="newMeeting.name">
            <label>Opis</label>
            <textarea v-model="newMeeting.description"></textarea>
            <button @click ="toogle">Dodaj</button>
            <label id="emptyState" v-if="!flag"> Spotkanie musi miec nazwe</label>
        </form>
</template>

<script>
export default {
  data() {
      return {
          flag: true,
          newMeeting: {
          participants: []
          }
          
      };
  },
  methods: {
      addNewMeeting() {
      if(this.newMeeting.name!=undefined && this.newMeeting.name.length>0)
      {
        this.$emit('added', this.newMeeting);
        this.newMeeting = {participants: []};

        }else
        {
        this.flag = false;
        }
    },
    toogle(){
    this.$emit('switchAgain', '');

    }
  }
}
</script>