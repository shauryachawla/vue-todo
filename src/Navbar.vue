<template>
  <div class="nav">
    <div class="nav-container">
      <div class="nav-child">
        <a href="#">Home</a>
      </div>
      <div class="nav-child">
        <a href="#">About</a>
      </div>
      <div class="nav-child">
        <a href="#">Login</a>
      </div>
      <div class="nav-child">
        <input @keyup="handleChange" type="text" v-model="searchedItem" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
      handleChange() {
          this.$emit('navToApp', this.searchedItem)
      }
  },
  data() {
    return {
      searchedItem: ""
    };
  }
};
</script>

<style>
.nav-container {
  display: flex;
  justify-content: space-evenly;
}

.nav-child {
}
</style>