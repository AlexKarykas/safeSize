<template>
  <b-navbar
    v-bind:class="
      rightSidebar ? 'navbar--custom' : 'navbar--custom custom-navbar--lg'
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
            <b-avatar
              icon="basket"
              class="cart-avatar"
              variant="primary"
            ></b-avatar>
          </div>
          <b-avatar
            class="name-avatar d-block d-sm-none"
            variant="light"
            text="AM"
          ></b-avatar>
          <b-avatar
            icon="chevron-down"
            class="chevron-avatar d-none d-sm-block"
            variant="primary"
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
.navbar--custom.navbar {
  position: sticky;
  top: 0;
  left: 0;
  width: 100%;
  background: $white;
  border-radius: 0 0 15px 15px;
  box-shadow: $shadow-lg;
}

.custom-navbar--lg {
  z-index: 10000;
}

.navbar__text {
  margin-bottom: 0;
  margin-left: 0.6rem;
  font-weight: bold;
}
.navbar__filters--hidden {
  opacity: 0;
}

.name-avatar {
  box-shadow: $shadow;
  background-color: $white;
}

.cart-avatar {
  margin: 0 0.6rem;
  box-shadow: $shadow;
  background-color: $lightblue;
}

.chevron-avatar {
  margin: 0 0.6rem;
  padding-top: 0.5rem;
  box-shadow: $shadow;
  background-color: $lightblue;
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