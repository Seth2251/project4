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
      <h2>Add your New Task</h2>
      <form @submit.prevent="addTask">
        <input v-model="taskTitle" placeholder="Please Enter a New Task" required />
        <button type="submit">Add Task</button>
      </form>
    </div>
  </template>
  
  
  
  <style scoped>
  input {
  padding: 8px;
  margin-right: 12px;
  font-size: 16px; /* Larger text */
}

button {
  padding: 8px 16px; 
  background-color: black; 
  color: green; 
  border: none;
  border-radius: 4px; 
}

button:hover {
  background-color: purple; 
}
  </style>