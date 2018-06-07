<template>
    <div>
     
       <button @click="show()">Dodaj nowe spotkanie</button>
       <new-meeting-form v-if="showForm" @switchAgain="show($event)" @added="addNewMeeting($event)"></new-meeting-form>
       <p v-show="!meetings[0]">Brak zaplanowanych spotkan</p>
        <p v-show="meetings[0]" >Zaplanowane zajecia ({{meetings.length}})</p>
       <meetings-list :meetings="meetings" :mail = "username"></meetings-list>
    </div>
</template>

<script>

import NewMeetingForm from "./NewMeetingForm";
import MeetingsList from "./MeetingsList";

export default {
props: ['username'],
  components: {NewMeetingForm, MeetingsList},
  
  data() {
      return {
          showForm: false,
          meetings: []
      };
  },
  methods: {
      addNewMeeting(meeting) {
          this.meetings.push(meeting);
      },
      show() {
          this.showForm = !this.showForm;
      }
      
  }
}
</script>