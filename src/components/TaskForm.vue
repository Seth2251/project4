<script>
  export default {
    data() {
      return {
        taskTitle: ''
      };
    },
    methods: {
      addTask() {
        if (this.taskTitle) {
          this.$emit('add-task', { title: this.taskTitle, completed: false, id: Date.now() });
          this.taskTitle = ''; 
        }
      }
    }
  };
  </script>


<template>
    <div>
      <h2>Add a New Task</h2>
      <form @submit.prevent="addTask">
        <input v-model="taskTitle" placeholder="Task title" required />
        <button type="submit">Add Task</button>
      </form>
    </div>
  </template>
  
  
  
  <style scoped>
  input {
    padding: 5px;
    margin-right: 10px;
  }
  button {
    padding: 5px;
  }
  </style>