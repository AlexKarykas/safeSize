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
import Home from "./components/homeScreen/Home.vue";
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
      smBreakpoint: 480,//576,
    };
  },
  methods: {
    toggleSmallScreenSidebar(isSmallScreen) {
      if (isSmallScreen.matches === true) {
        this.showBackdrop = true;
        this.showRightSidebar = true;
      }
    },

    toggleLargeScreenSidebar(isLargeScreen) {
      if (isLargeScreen.matches === true) {
        this.showBackdrop = false;
        this.showRightSidebar = false;
      }
    },
  },
  mounted() {
    this.$root.$on("bv::collapse::state", (collapseId, isOpen) => {
      if (collapseId === "sidebar") {
        this.isOpen = isOpen;
      }
    });

    const isSmallScreen = window.matchMedia(
      `(max-width: ${this.smBreakpoint}px)`
    );
    this.toggleSmallScreenSidebar(isSmallScreen);
    isSmallScreen.onchange = () => {
      this.toggleSmallScreenSidebar(isSmallScreen);
    };

    const isLargeScreen = window.matchMedia(
      `(min-width: ${this.smBreakpoint}px)`
    );
    this.toggleLargeScreenSidebar(isLargeScreen);
    isLargeScreen.onchange = () => {
      this.toggleLargeScreenSidebar(isLargeScreen);
    };
  },
  unmounted() {
    const isSmallScreen = window.matchMedia(
      `(max-width: ${this.smBreakpoint}px)`
    );
    this.toggleSmallScreenSidebar(isSmallScreen);
    isSmallScreen.onchange = () => {
      this.toggleSmallScreenSidebar(isSmallScreen);
    };

    const isLargeScreen = window.matchMedia(
      `(min-width: ${this.smBreakpoint}px)`
    );
    this.toggleLargeScreenSidebar(isLargeScreen);
    isLargeScreen.onchange = () => {
      this.toggleLargeScreenSidebar(isLargeScreen);
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
  transition: all $b-sidebar-transition-duration ease-in;
}

.home--push-right {
  margin-left: calc($b-sidebar-width + 1rem);
  transition: margin $b-sidebar-transition-duration ease-out;
}

.home--push-left {
  overflow: hidden;
  margin-left: -$b-sidebar-width;
  opacity: 0;
  max-height: 50vh;
  transition: all $b-sidebar-transition-duration ease-out;
}
</style>
