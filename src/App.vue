<template>
  <div id="app" v-bind:class="isOpen ? 'home--push' : 'home--push-back'">
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
  data() {
    return {
      isOpen: false,
    };
  },
  mounted() {
    this.$root.$on("bv::collapse::state", (collapseId, isOpen) => {
      if (collapseId === "sidebar") {
        this.isOpen = isOpen;
      }
    });
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
  letter-spacing: 0.5px;
  color: $text-color;
  background-color: #f5f7f8;
}

.home--push-back {
  margin-left: inherit;
  transition: margin 300ms ease-in;
}

.home--push {
  margin-left: 320px;
  transition: margin 300ms ease-out;
}
</style>
