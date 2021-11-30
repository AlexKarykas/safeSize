<template>
  <div w-25 p-3>
    <b-navbar class="custom-navbar">
      <div v-b-toggle.sidebar class="d-block d-sm-none">
        <b-container>
          <b-row align-v="center">
            <b-icon icon="filter"></b-icon>
            <p class="sidebar-toggle-button-left">FILTERS</p>
          </b-row>
        </b-container>
      </div>
      <div v-b-toggle.sidebar class="d-none d-sm-block">
        <b-img src="../../public/logo.png" alt="Logo" height="48px"></b-img>
      </div>

      <b-navbar-nav class="ml-auto">
        <b-nav-form>
          <p class="d-none d-sm-block">Aristotelis Michailidis</p>
          <b-avatar
            icon="basket"
            class="cart-avatar"
            variant="primary"
          ></b-avatar>
          <b-avatar
            class="name-avatar d-block d-sm-none"
            variant="light"
            text="AM"
          ></b-avatar>
          <b-avatar
            icon="chevron-compact-down"
            class="cart-avatar d-none d-sm-block"
            variant="primary"
          ></b-avatar>
        </b-nav-form>
      </b-navbar-nav>
    </b-navbar>

    <b-sidebar id="sidebar" left shadow>
      <div class="sidebar-basic">
        <b-container>
          <b-row align-h="between" class="d-none d-sm-block">
            <b-icon icon="chevron-compact-left"></b-icon>
            <h2 class="sidebar-header">Our recommendations</h2>
          </b-row>
          <b-row align-h="between">
            <h4 class="menu-header">Functional Advice</h4>
            <b-form-checkbox switch class="mr-n2"> </b-form-checkbox>
          </b-row>
        </b-container>
        <b-container>
          <b-row align-h="between" class="drawer-rectangle">
            <p>CATEGORY: ROAD</p>
            <b-icon icon="info-circle-fill" variant="primary"></b-icon>
          </b-row>
          <b-row align-h="between" class="drawer-rectangle">
            <p>CUSHIONING: CUSHIONING</p>
            <b-icon icon="info-circle-fill" variant="primary"></b-icon>
          </b-row>
          <b-row align-h="between" class="drawer-rectangle">
            <p>STABILITY: STABLE+</p>
            <b-icon icon="info-circle-fill" variant="primary"></b-icon>
          </b-row>
        </b-container>
        <b-input-group class="sidebar-search-box">
          <b-form-input
            type="search"
            placeholder="Search shoes..."
            class="search-box"
          >
          </b-form-input>
          <b-input-group-append class="search-icon">
            <b-icon icon="search" variant="primary"></b-icon>
          </b-input-group-append>
        </b-input-group>
        <Filters />
        <b-button class="btn-remove" variant="light">Remove All</b-button>
        <b-button class="btn-apply" variant="primary">Apply</b-button>
      </div>
    </b-sidebar>
  </div>
</template>

<script>
import Filters from "./Filters.vue";
export default {
  name: "Drawer",
  components: { Filters },
};
</script>

<style>
.d-sm-block {
  display: inline-block;
}
.search-box,
.search-box:focus {
  border: none;
  border-bottom: 1px solid #e7e7e7;
  background: inherit;
  outline: none;
  box-shadow: none;
}

.sidebar-header {
  padding: 0.25rem;
  font-size: 1.6rem;
  text-align: left;
}

.sidebar-basic {
  padding: 1rem;
}

.search-icon {
  position: absolute;
  right: 3%;
  top: 30%;
}

.custom-navbar {
  background: #fff;
  border-radius: 0 0 15px 15px;
}

.sidebar-toggle-button-left {
  margin-bottom: 0;
  margin-left: 0.6rem;
  font-weight: bold;
}

.sidebar-search-box {
  margin: 2rem 0;
  outline: none;
}

.name-avatar {
  display: inline-block;
  box-shadow: 1px 1px 2px 0 rgba(0, 0, 0, 0.18),
    0 1.1px 5px 0 rgba(0, 0, 0, 0.2);
  background-color: #fff;
}

.cart-avatar {
  margin-right: 0.6rem;
  box-shadow: 1px 1px 2px 0 rgba(0, 0, 0, 0.18),
    0 1.1px 5px 0 rgba(0, 0, 0, 0.2);
  background-color: #3ea3dc;
}

.drawer-rectangle {
  margin: 0.6rem 0;
  padding: 0.4rem 1rem;
  border-radius: 0.5rem;
  background-color: #d8edf8;
}

.drawer-rectangle p {
  margin-bottom: 0;
  font-size: 1rem;
  font-weight: 500;
  text-align: left;
  color: #006eb7;
}

.btn-remove {
  width: 7.8rem;
  height: 3rem;
  margin: 3%;
  font-weight: bold;
  color: #006eb7;
  box-shadow: 1px 1px 2px 0 rgba(0, 0, 0, 0.18),
    0 1.1px 5px 0 rgba(0, 0, 0, 0.2);
  background-color: #fff;
}

.btn-apply {
  width: 7.8rem;
  height: 3rem;
  margin: 3%;
  font-weight: bold;
  color: #fff;
  box-shadow: 1px 1px 2px 0 rgba(0, 0, 0, 0.18),
    0 1.1px 5px 0 rgba(0, 0, 0, 0.2);
  background-color: #fff;
}
</style>
