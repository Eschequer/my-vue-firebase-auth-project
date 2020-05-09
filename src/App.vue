<template>
  <div id="app">
    <app-header></app-header>
    <router-view />
  </div>
</template>

<script>
import Header from "@/components/Header";

export default {
  name: "App",
  components: {
    AppHeader: Header
  }
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 5px;
  padding: 10px;
}
</style>
