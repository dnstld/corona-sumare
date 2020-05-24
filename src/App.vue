<template>
  <div id="app">
    <CoronaPanel />
  </div>
</template>

<script>
import CoronaPanel from "./components/CoronaPanel.vue";

export default {
  name: "App",
  components: {
    CoronaPanel
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
  margin-top: 60px;
}
</style>
