<template>
  <div class="active-tasks">
    <h3>Active tasks</h3>
    <ol>
      <li v-for="task in activeTasks" :key="task.id">{{task.title}}</li>
    </ol>
  </div>
</template>

<script>
export default {
  methods: {
    testData() {
      console.log(this.activeTasks);
    }
  },
  props: ["activeTasks"],
  data() {
    return {};
  }
};
</script>

<style>
</style>