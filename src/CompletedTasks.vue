<template>
  <div class="completed-tasks">
    <h3>Completed tasks</h3>
    <ol>
        <li v-for="task in completedTasks" :key="task.id">{{task.title}}</li>
    </ol>
  </div>
</template>

<script>
export default {
    props:['completedTasks'],
    data() {
        return {
            
        }
    },
};
</script>

<style>
</style>