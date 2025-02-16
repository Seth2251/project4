<template>
    <div>
      <h2>Your Tasks</h2>
      <ul>
        <li v-for="task in tasks" :key="task.id">
          <span :class="{'line-through': task.completed}">{{ task.title }}</span>
          <button @click="toggleCompletion(task)">Mark as {{ task.completed ? 'Incomplete' : 'Completed' }}</button>
          <button @click="deleteTask(task.id)">Delete</button>
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    props: ['tasks'],
    methods: {
      toggleCompletion(task) {
        this.$emit('toggle-completion', task.id);
      },
      deleteTask(taskId) {
        this.$emit('delete-task', taskId);
      }
    }
  };
  </script>
  
  <style scoped>
  button {
    margin-left: 10px;
  }
  .line-through {
    text-decoration: line-through;
  }
  </style>