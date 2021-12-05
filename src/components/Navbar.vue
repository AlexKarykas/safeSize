<template>
  <b-navbar
    v-bind:class="
      rightSidebar
        ? 'navbar--custom navbar--custom--sm'
        : 'navbar--custom navbar--custom--lg'
    "
  >
    <div v-b-toggle.sidebar class="d-block d-sm-none">
      <b-container
        v-bind:class="sidebarIsOpen ? 'navbar__filters--hidden' : ''"
      >
        <b-row align-v="center">
          <b-icon icon="filter"></b-icon>
          <p class="navbar__text">FILTERS</p>
        </b-row>
      </b-container>
    </div>
    <div v-b-toggle.sidebar class="d-none d-sm-block">
      <b-img src="../../public/logo.png" alt="Logo" height="48px"></b-img>
    </div>

    <b-navbar-nav class="ml-auto">
      <b-container>
        <b-row align-v="center">
          <p class="navbar__text d-none d-sm-block">{{ username }}</p>
          <div>
            <b-badge class="navbar__orders__badge" pill variant="light">{{
              orders
            }}</b-badge>
            <b-avatar icon="basket" id="navbar__avatar--cart"></b-avatar>
          </div>
          <b-avatar
            class="navbar__avatar--name d-block d-sm-none"
            variant="light"
            text="AM"
          ></b-avatar>
          <b-avatar
            id="navbar__avatar--chevron"
            icon="chevron-down"
            class="d-none d-sm-block"
            variant="light"
            v-b-toggle.sidebar
          ></b-avatar>
        </b-row>
      </b-container>
    </b-navbar-nav>
  </b-navbar>
</template>

<script>
export default {
  name: "Navbar",
  props: ["rightSidebar", "sidebarIsOpen"],
  data() {
    return {
      username: "Aristotelis Michailidis",
      orders: 0,
    };
  },
};
</script>

<style lang="scss">
.navbar.navbar--custom {
  position: sticky;
  top: 0;
  left: 0;
  width: 100%;
  background: $white;
  border-radius: 0 0 15px 15px;
  box-shadow: $shadow-lg;
}

.navbar--custom--sm {
  z-index: calc($b-sidebar-zindex - 5);
}

.navbar--custom--lg {
  z-index: calc($b-sidebar-zindex + 5);
}

.navbar__text {
  margin-bottom: 0;
  margin-left: 0.6rem;
  font-weight: bold;
}
.navbar__filters--hidden {
  opacity: 0;
}

.navbar__avatar--name {
  box-shadow: $shadow;
  background-color: $white;
}

#navbar__avatar--cart {
  margin: 0 0.6rem;
  box-shadow: $shadow;
  background-color: $lightblue;
}

#navbar__avatar--chevron {
  margin: 0 0.6rem;
  padding-top: 0.5rem;
  box-shadow: $shadow;
  color: $lightblue;
}

.navbar__orders__badge {
  position: relative;
  top: -1.1rem;
  left: 1.4rem;
  border: 1px solid $lightblue;
  background: $white;
  z-index: 1;
}
</style>