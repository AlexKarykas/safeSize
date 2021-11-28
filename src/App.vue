<template>
  <div id="app">
    <Drawer title="Recommendations" />
    <Home />
  </div>
</template>

<script>
import Home from "./components/Home.vue";
import Drawer from "./components/Drawer.vue";

export default {
  name: "App",
  components: {
    Home,
    Drawer,
  },
};
</script>

<style lang="scss">
@import "~@/assets/scss/vendors/bootstrap-vue/index";
#app {
  font-family: Heebo, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: #f5f7f8;
}
</style>
