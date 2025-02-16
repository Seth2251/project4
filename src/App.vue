<script>
import TaskForm from './components/TaskForm.vue';
import TaskList from './components/TaskList.vue';
import TaskStats from './components/TaskStats.vue';

export default {
components: {
    TaskForm,
    TaskList,
    TaskStats
  },
  data() {
    return {
      tasks: []
    };
  },
  methods: {
  addTask(task) {
      this.tasks.push(task);
    },
  toggleCompletion(taskId) {
      const task = this.tasks.find(t => t.id === taskId);
      if (task) {
        task.completed = !task.completed;
      }
    },
  deleteTask(taskId) {
      this.tasks = this.tasks.filter(t => t.id !== taskId);
    }
  }
};
</script>


<template>
  <div>
    <h1>Welcome to the Task Tracker</h1>
    <TaskForm @add-task="addTask" />
    <TaskList :tasks="tasks" @toggle-completion="toggleCompletion" @delete-task="deleteTask" />
    <TaskStats :tasks="tasks" />
  </div>
</template>
