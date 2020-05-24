<template>
  <div id="app">
    <PanelOverview />
  </div>
</template>

<script>
import PanelOverview from "./components/PanelOverview.vue";

export default {
  name: "App",
  components: {
    PanelOverview
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
