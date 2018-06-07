<template>
    <table v-if="meetings.length > 0">
        <thead>
            <tr>
                <th>Nazwa spotkania</th>
                <th>Opis</th>
                <th>Uczestnicy</th>
                
            </tr>
        </thead>
        <tbody>
            <tr v-for="meeting in meetings" :key="meeting.name">
                <td>{{ meeting.name }}</td>
                <td>{{ meeting.description }}</td>
                 <td>
                   
                     <ul v-for="participant in meeting.participants">
                           <li>{{participant}}</li>
                     </ul>
                     
               </td>
                
                <td v-if="!meeting.participants.includes(mail)" >
                    <button @click="add(meeting)">zapisz sie</button>
                    <button @click="remove(meeting)">usun puste spotkanie</button></td>
                    <td v-else><button @click="signOut(meeting)">wypisz sie</button> 
               </td>
            </tr>
        </tbody>
    </table>
</template>

<script>
export default {
    props: ['meetings', 'mail', 'participants'],
 
     methods: {
     remove(meeting) {
      if (!meeting.participants.length > 0) {
        this.meetings = this.meetings.splice(this.meetings.indexOf(meeting));
      }
      return this.meetings;
    }, 
    
    add(meeting) {
      return meeting.participants.push(this.mail);
    },
    signOut(meeting) {
      return meeting.participants.splice(
        meeting.participants.indexOf(this.mail)
      );
    }
  }
}
</script>