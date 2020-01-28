<template>
  <div class="todo-app">
    <Navbar @navToApp="navToApp"/>
    <p>Searched Item: {{searchedItem}}</p>
    <ActiveTasks :activeTasks="activeTasks" />
    <CompletedTasks :completedTasks="completedTasks" />
  </div>
</template>

<script>
import axios from "axios";
import ActiveTasks from "./ActiveTasks";
import CompletedTasks from "./CompletedTasks";
import Navbar from "./Navbar";
export default {
  methods: {
      navToApp(payload) {
          this.searchedItem = payload
      }
  },
  props: [],
  computed: {
    activeTasks() {
      return this.todos.filter(todo => {
          if(todo.title.match(this.searchedItem) && !todo.completed) return todo
      });
    },
    completedTasks() {
      return this.todos.filter(todo => {
        if(todo.title.match(this.searchedItem) && todo.completed) return todo
      });
    }
  },
  data() {
    return {
      todos: [],
      searchedItem: ""
    };
  },
  components: {
    ActiveTasks,
    CompletedTasks,
    Navbar
  },
  created() {
    axios
      .get("https://jsonplaceholder.typicode.com/todos/")
      .then(Response => {
        //   console.log(Response);
        this.todos = Response.data;
      })
      .catch(err => {
        console.log(err);
      });
  }
};
</script>

<style>
</style>