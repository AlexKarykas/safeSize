<template>
  <div w-25 p-3>
    <Navbar />
    <b-sidebar id="sidebar" left shadow no-header>
      <template #default="{ hide }">
        <div class="sidebar-basic">
          <b-container>
            <b-row @click="hide" class="d-none d-sm-block">
              <b-icon icon="chevron-left"></b-icon>
              <h2 class="sidebar-header">Our recommendations</h2>
            </b-row>
            <b-row align-h="between">
              <h4 class="menu-header">Functional Advice</h4>
              <b-form-checkbox switch class="mr-n2"> </b-form-checkbox>
            </b-row>
          </b-container>
          <b-container>
            <b-row align-h="between" class="drawer__rectangle">
              <p>CATEGORY: ROAD</p>
              <b-icon icon="info-circle-fill" variant="primary"></b-icon>
            </b-row>
            <b-row align-h="between" class="drawer__rectangle">
              <p>CUSHIONING: CUSHIONING</p>
              <b-icon icon="info-circle-fill" variant="primary"></b-icon>
            </b-row>
            <b-row align-h="between" class="drawer__rectangle">
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
          <b-button class="drawer__btn drawer__btn--remove" variant="light"
            >Remove All</b-button
          >
          <b-button class="drawer__btn drawer__btn--apply" variant="primary"
            >Apply</b-button
          >
        </div>
      </template>
    </b-sidebar>
  </div>
</template>

<script>
import Filters from "./Filters.vue";
import Navbar from "./Navbar.vue";
export default {
  name: "Drawer",
  components: { Filters, Navbar },
};
</script>

<style lang="scss">
.d-sm-block {
  display: inline-block;
}
.search-box,
.search-box:focus {
  border: none;
  border-bottom: 1px solid $gray-border;
  background: inherit;
  outline: none;
  box-shadow: none;
}

.sidebar-header {
  display: inline-block;
  padding: 0.25rem;
  font-size: 1.3rem;
  text-align: left;
}

.sidebar-basic {
//   padding: 1rem;
  margin: 1rem;
}

.search-icon {
  position: absolute;
  right: 3%;
  top: 30%;
}

.sidebar-search-box {
  margin: 2rem 0;
  outline: none;
}

.drawer__rectangle {
  margin: 0.6rem 0;
  padding: 0.4rem 1rem;
  border-radius: 0.5rem;
  background-color: $blue-background;
  p {
    margin-bottom: 0;
    font-size: 1rem;
    font-weight: 500;
    text-align: left;
    color: $blue;
  }
}

.drawer__btn {
  width: 7.8rem;
  height: 3rem;
  margin: 3%;
  font-weight: bold;
}
.drawer__btn--remove {
  color: $blue;
  box-shadow: $shadow;
  background-color: $white;
}

.drawer__btn--apply {
  color: $white;
  box-shadow: $shadow;
  background-color: $white;
}
</style>
