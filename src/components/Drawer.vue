<template>
  <div w-25 p-3>
    <b-navbar class="custom-navbar">
      <div v-b-toggle.sidebar>
        <div class="sidebar-toggle-button-left">
          <b-icon icon="filter"></b-icon>
          <p>FILTERS</p>
        </div>
      </div>

      <!-- Right aligned nav items -->
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

    <b-sidebar id="sidebar" title="Functional Advice" left shadow>
      <b-form-checkbox switch class="mr-n2"> </b-form-checkbox>
      <div>
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
          <b-form-input
            v-model="text"
            type="search"
            placeholder="Search shoes..."
          >
          </b-form-input>
          <b-input-group-append>
            <b-button variant="outline-primary"
              ><b-icon icon="search" variant="primary"></b-icon
            ></b-button>
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
  margin: 3%;
  outline: non;
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
  margin: 1% 5%;
  padding: 1% 4%;
  width: 90%;
  border-radius: 6.3px;
  background-color: #d8edf8;
}

.drawer-rectangle p {
  margin-bottom: 0;
  font-size: 1rem;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: normal;
  letter-spacing: 0.5px;
  text-align: left;
  color: #006eb7;
}

.btn-remove {
  width: 30%;
  margin: 3%;
  font-weight: bold;
  font-stretch: normal;
  font-style: normal;
  line-height: normal;
  letter-spacing: 0.5px;
  text-align: center;
  color: #006eb7;
  box-shadow: 1px 1px 2px 0 rgba(0, 0, 0, 0.18),
    0 1.1px 5px 0 rgba(0, 0, 0, 0.2);
  background-color: #fff;
}

.btn-apply {
  width: 30%;
  margin: 3%;
  font-weight: bold;
  font-stretch: normal;
  font-style: normal;
  line-height: normal;
  letter-spacing: 0.5px;
  text-align: center;
  color: #fff;
  box-shadow: 1px 1px 2px 0 rgba(0, 0, 0, 0.18),
    0 1.1px 5px 0 rgba(0, 0, 0, 0.2);
  background-color: #fff;
}
</style>
