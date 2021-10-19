<template>
  <div class="container">
    <Header title="Task Tracker"/>
    <Add />
    <Tasks @delete-task="deleteTask" @toggle-reminder="toggleReminder" :tasks="tasks"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Tasks from './components/Tasks.vue'
import Add from './components/Add.vue'

export default {
  name: "App",
  components: {
    Header,
    Tasks,
    Add
  },
  data(){
    return {
      tasks: []
    }
  },
  methods: {
    deleteTask(id){
      if (confirm('Are you sure to delete this item?')){
        this.tasks = this.tasks.filter(task => task.id !== id)
      }
    },
    toggleReminder(id){
      this.tasks = this.tasks.map(task => task.id === id ? {...task, reminder:!task.reminder} : task)
    }
  },
  created(){
    this.tasks = [
      {
        "id": 1,
        "text": "doctor appointment",
        "day": "2021-10-18",
        "reminder": true
      },
      {
        "id": 2,
        "text": "interview appointment",
        "day": "2021-2-3",
        "reminder": true
      },
      {
        "id": 3,
        "text": "meeting appointment",
        "day": "2021-11-8",
        "reminder": true
      }
    ]
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
