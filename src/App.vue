<template>
    <div class="container">
        <Header title="Task Tracker" @toggle-add-task = "toggleAddTaskForm" :showAddTask="showAddTask"/>
        <div v-show="showAddTask">
          <AddTask @save-task = "saveTask"/>
        </div>
        <EmptyTask  v-if = "tasks.length === 0"/>
        <Tasks v-else @delete-task = "deleteTask" @toggle-reminder = "toggleTaskReminder" :tasks="tasks"/>
    </div>
</template>

<script>
import Header from "./components/Header.vue";
import Tasks from "./components/Tasks.vue";
import AddTask from "./components/AddTask.vue";
import EmptyTask from "./components/EmptyTask.vue";

export default {
  name: 'App',
  components:{
    Header,
    Tasks,
    AddTask,
    EmptyTask,
  },
  data(){
    return{
      tasks:[],
      showAddTask:false,
    }
  },

  emits:["delete-task","toggle-reminder","toggle-add-task","save-task"],

  methods:{
    deleteTask(id) {
      this.tasks = this.tasks.filter(task=>task.id !== id);
    },
    toggleTaskReminder(id){
      this.tasks = this.tasks.map((task)=>
      task.id === id ? {...task,reminder:!task.reminder}:task
      )
    },
    toggleAddTaskForm(){
      this.showAddTask = !this.showAddTask;
    },
    saveTask(task){
      this.tasks = [...this.tasks,task];
    }
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
  max-height: 100vh;
  border: 1px solid #ddd;
  margin: 2rem auto;
  padding: 1rem;
  background-color: rgb(240, 230, 230);
}
@media screen and (max-width: 600px) {
  .container {
     width: 85vw;
  }
}
@media screen and (min-width: 600px) {
  .container {
     width: 75vw;
  }
}
@media screen and (min-width: 768px) {
  .container {
     width: 60vw;
  }
}
@media only screen and (min-width: 992px) {
  .container {
     width: 40vw;
  }
}
@media only screen and (min-width: 1300px) {
  .container {
    width: 25vw;
  }
}
</style>
