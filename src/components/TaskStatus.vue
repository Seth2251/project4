<script>
export default {
  props: ['tasks'],
  computed: {
    totalTasks() {
      return this.tasks.length;
    },
    completedTasks() {
      return this.tasks.filter(task => task.completed).length;
    },
    completionRate() {
      return this.totalTasks > 0 ? ((this.completedTasks / this.totalTasks) * 100).toFixed(2) : 0;
    }
  }
};
</script>

<template>
    <div>
      <h2>Task Stats</h2>
      <p>Total Tasks: {{ totalTasks }}</p>
      <p>Completed Tasks: {{ completedTasks }}</p>
      <p>Completion Rate: {{ completionRate }}%</p>
    </div>
  </template>

<style scoped>
p {
  margin: 5px 0;
}
</style>