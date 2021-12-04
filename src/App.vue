<template>
  <div id="app">
    <Navbar
      v-bind:rightSidebar="showRightSidebar"
      v-bind:sidebarIsOpen="isOpen"
    />
    <Sidebar
      v-bind:showBackdrop="showBackdrop"
      v-bind:showRight="showRightSidebar"
    />
    <Home
      v-bind:class="
        isOpen
          ? showRightSidebar
            ? 'home--push-left'
            : 'home--push-right'
          : 'home--push-back'
      "
    />
  </div>
</template>

<script>
import Home from "./components/Home.vue";
import Navbar from "./components/Navbar.vue";
import Sidebar from "./components/sidebar/Sidebar.vue";

export default {
  name: "App",
  components: {
    Home,
    Navbar,
    Sidebar,
  },
  data() {
    return {
      isOpen: false,
      showBackdrop: false,
      showRightSidebar: false,
    };
  },
  mounted() {
    this.$root.$on("bv::collapse::state", (collapseId, isOpen) => {
      if (collapseId === "sidebar") {
        this.isOpen = isOpen;
      }
    });
    const smallScreenQuery = window.matchMedia("(max-width: 576px)");
    console.log("smallScreenQuery " + smallScreenQuery);
    smallScreenQuery.onchange = () => {
      if (smallScreenQuery.matches === true) {
        this.showBackdrop = true;
        this.showRightSidebar = true;
      }
    };
    const largeScreenQuery = window.matchMedia("(min-width: 576px)");
    console.log("largeScreenQuery " + largeScreenQuery);
    largeScreenQuery.onchange = () => {
      if (largeScreenQuery.matches === true) {
        this.showBackdrop = false;
        this.showRightSidebar = false;
      }
    };
    console.log("this.showBackdrop " + this.showBackdrop);
    console.log("this.showRightSidebar " + this.showRightSidebar);
  },
  unmounted() {
    const smallScreenQuery = window.matchMedia("(max-width: 576px)");
    smallScreenQuery.onchange = () => {
      if (smallScreenQuery.matches === true) {
        this.showBackdrop = true;
        this.showRightSidebar = true;
      }
    };
    const largeScreenQuery = window.matchMedia("(min-width: 576px)");
    largeScreenQuery.onchange = () => {
      if (largeScreenQuery.matches === true) {
        this.showBackdrop = false;
        this.showRightSidebar = false;
      }
    };
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
  transition: all 300ms ease-in;
}

.home--push-right {
  margin-left: 320px;
  transition: margin 300ms ease-out;
}

.home--push-left {
  margin-left: -320px;
  opacity: 0;
  transition: all 300ms ease-out;
}
</style>
