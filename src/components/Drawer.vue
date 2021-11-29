<template>
  <div w-25 p-3>
    <b-navbar class="custom-navbar">
      <div v-b-toggle.sidebar>
        <div class="sidebar-toggle-button-left">
          <b-icon icon="filter"></b-icon>
          <p>FILTERS</p>
        </div>
      </div>

      <b-navbar-nav class="ml-auto">
        <b-nav-form>
          <div class="sidebar-toggle-button-right">
            <b-avatar
              icon="basket"
              class="cart-avatar"
              variant="primary"
            ></b-avatar>
            <b-avatar class="name-avatar" variant="light" text="AM"></b-avatar>
          </div>
        </b-nav-form>
      </b-navbar-nav>
    </b-navbar>

    <b-sidebar id="sidebar" left shadow>
      <div class="sidebar-basic">
        <b-container>
          <!-- <b-row>
          <b-icon class="when-closed" icon="chevron-compact-left"></b-icon>
          Our recommendations
        </b-row> -->
          <b-row class="justify-content-between">
            <h4 class="menu-header">Functional Advice</h4>
            <b-form-checkbox switch class="mr-n2"> </b-form-checkbox>
          </b-row>
        </b-container>
        <div class="drawer-rectangle">
          <p>CATEGORY: ROAD</p>
          <b-icon icon="info-circle-fill" variant="primary"></b-icon>
        </div>
        <div class="drawer-rectangle">
          <p>CUSHIONING: CUSHIONING</p>
          <b-icon icon="info-circle-fill" variant="primary"></b-icon>
        </div>
        <div class="drawer-rectangle">
          <p>STABILITY: STABLE+</p>
          <b-icon icon="info-circle-fill" variant="primary"></b-icon>
        </div>
        <b-input-group class="sidebar-search-box">
          <b-form-input type="search" placeholder="Search shoes...">
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
  display: flex;
  flex-direction: row;
  align-items: center;
}

.sidebar-toggle-button-left p {
  margin-bottom: 0;
  margin-left: 10px;
  font-weight: bold;
}

.sidebar-search-box {
  margin: 2rem 0;
  outline: none;
}

.name-avatar {
  box-shadow: 1px 1px 2px 0 rgba(0, 0, 0, 0.18),
    0 1.1px 5px 0 rgba(0, 0, 0, 0.2);
  background-color: #fff;
}

.cart-avatar {
  margin-right: 10px;
  box-shadow: 1px 1px 2px 0 rgba(0, 0, 0, 0.18),
    0 1.1px 5px 0 rgba(0, 0, 0, 0.2);
  background-color: #3ea3dc;
}

.drawer-rectangle {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
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
