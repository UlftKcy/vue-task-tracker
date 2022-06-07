<template>
    <div class="container">
        <Header title="Task Tracker"/>
        <AddTask/>
        <Tasks @delete-task = "deleteTask" @toggle-reminder = "toggleTaskReminder" :tasks="tasks"/>
    </div>
</template>

<script>
import Header from "./components/Header.vue";
import Tasks from "./components/Tasks.vue";
import AddTask from "./components/AddTask.vue";

export default {
  name: 'App',
  components:{
    Header,
    Tasks,
    AddTask,
  },
  data(){
    return{
      tasks:[]
    }
  },

  emits:["delete-task","toggle-reminder"],

  methods:{
    deleteTask(id) {
      this.tasks = this.tasks.filter(task=>task.id !== id);
    },
    toggleTaskReminder(id){
      this.tasks = this.tasks.map((task)=>
      task.id === id ? {...task,reminder:!task.reminder}:task
      )
    },
  },

  created(){
    this.tasks = [
      {
        id:1,
        text:"Doctors Appointment",
        day:"June 21st at 2:30pm",
        reminder:true,
      },
      {
        id:2,
        text:"Meeting at School",
        day:"June 11st at 3:30pm",
        reminder:true,
      },
      {
        id:3,
        text:"Food Shopping",
        day:"June 23rd at 12:30pm",
        reminder:false,
      }
    ]
  }
}
</script>
<style>
.container{
  width: 25vw;
  min-height: 80vh;
  border: 1px solid #ddd;
  margin: 2rem auto;
  padding: 1rem;
  background-color: rgb(240, 230, 230);
}
</style>
