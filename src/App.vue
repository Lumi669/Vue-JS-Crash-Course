<template>
    <div class="container">
      <Header title="Task Tracker"/>
      <Tasks @delete-task="deleteTask" :tasks = "tasks"/>
    </div>
  
</template>




<script>
import Header from './components/header'
import Tasks from './components/tasks'

export default {
  name: 'App',
  components: {
    Header,
    Tasks
  },
  data(){
    return {
      tasks:[]
    }
  },
  methods:{
    deleteTask(id){
      if(confirm('are you sure?')){

        this.tasks = this.tasks.filter((task)=> task.id !== id)
      }
      }
    },

  

  created(){
    this.tasks = [
      
      {
        id:1,
        text:'Doctor appoint',
        day:'March 1st',
        reminder:true
      },
      {
        id:2,
        text:'teacher appoint',
        day:'April 1st',
        reminder:true
      },
      {
        id:3,
        text:'gym appoint',
        day:'May 1st',
        reminder:false
      }
    ]
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: 'Poppins', sans-serif;
}
.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}
.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
.btn:focus {
  outline: none;
}
.btn:active {
  transform: scale(0.98);
}
.btn-block {
  display: block;
  width: 100%;
}
</style>
