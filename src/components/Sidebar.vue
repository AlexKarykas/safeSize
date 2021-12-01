<template>
  <b-sidebar id="sidebar" no-header left shadow class="sidebar--custom">
    <template #default="{ hide }">
      <div class="sidebar-basic">
        <b-container>
          <b-row>
            <b-button-close
              @click="hide"
              class="d-inline-block d-sm-none drawer__close-button--sm"
            ></b-button-close>
          </b-row>
          <b-row @click="hide" class="d-none d-sm-inline-block">
            <b-icon icon="chevron-left"></b-icon>
            <h2 class="sidebar-header">Our recommendations</h2>
          </b-row>
          <b-row align-h="between">
            <h4 class="menu-header">Functional Advice</h4>
            <b-form-checkbox switch class="mr-n2"> </b-form-checkbox>
          </b-row>
        </b-container>
        <b-container class="drawer__rectangle__container">
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
          <b-input-group-append>
            <b-button class="search-box">
              <b-icon icon="search" variant="primary"></b-icon>
            </b-button>
          </b-input-group-append>
        </b-input-group>
        <SidebarFilters />
        <b-button class="drawer__btn drawer__btn--remove" variant="light"
          >Remove All</b-button
        >
        <b-button class="drawer__btn drawer__btn--apply" variant="primary"
          >Apply</b-button
        >
      </div>
    </template>
  </b-sidebar>
</template>

<script>
import SidebarFilters from "./filters/SidebarFilters.vue";
export default {
  name: "Drawer",
  components: { SidebarFilters },
};
</script>

<style lang="scss">
.search-box,
.search-box:focus {
  border: none;
  border-bottom: 1px solid $gray-border;
  background: inherit;
  outline: none;
  box-shadow: none;
}

.sidebar--custom {
  margin-left: 2rem;
}

.sidebar-header {
  display: inline-block;
  padding: 0.25rem;
  font-size: 1.3rem;
  text-align: left;
  &:hover {
    cursor: pointer;
  }
}

.sidebar-basic {
  margin: 1rem;
}

.sidebar-search-box {
  margin: 2rem 0;
  outline: none;
}

.drawer__rectangle__container {
  padding-right: 0;
  padding-left: 0;
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
  border-radius: 1rem;
}

.drawer__btn--remove {
  color: $blue;
  box-shadow: $shadow;
  background-color: $white;
}

.drawer__btn--apply {
  color: $white;
  box-shadow: $shadow;
  background-color: $blue;
}
</style>
