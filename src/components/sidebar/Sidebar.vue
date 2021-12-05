<template>
  <b-sidebar
    id="sidebar"
    no-header
    v-bind:backdrop="showBackdrop"
    v-bind:right="showRight"
    shadow
  >
    <template #default="{ hide }">
      <div class="sidebar-basic">
        <b-button-close
          si
          @click="hide"
          class="d-inline-block d-sm-none sidebar__close-btn"
        ></b-button-close>
        <b-container>
          <b-row @click="hide" class="d-none d-sm-inline-block">
            <b-icon icon="chevron-left"></b-icon>
            <h2 class="sidebar__header">Our recommendations</h2>
          </b-row>
          <b-row align-h="between">
            <h4 class="menu-header">Functional Advice</h4>
            <b-form-checkbox switch size="lg" class="mr-n2"> </b-form-checkbox>
          </b-row>
        </b-container>
        <b-container class="sidebar__rectangles__container">
          <b-row align-h="between" class="sidebar__rectangle">
            <p>CATEGORY: ROAD</p>
            <b-icon icon="info-circle-fill" variant="primary"></b-icon>
          </b-row>
          <b-row align-h="between" class="sidebar__rectangle">
            <p>CUSHIONING: CUSHIONING</p>
            <b-icon icon="info-circle-fill" variant="primary"></b-icon>
          </b-row>
          <b-row align-h="between" class="sidebar__rectangle">
            <p>STABILITY: STABLE+</p>
            <b-icon icon="info-circle-fill" variant="primary"></b-icon>
          </b-row>
        </b-container>
        <b-input-group class="sidebar__search-box">
          <b-form-input
            type="search"
            placeholder="Search shoes..."
            class="search-box"
          >
          </b-form-input>
          <b-input-group-append>
            <button class="search-box">
              <b-icon
                icon="search"
                variant="primary"
                class="search-box__button"
              ></b-icon>
            </button>
          </b-input-group-append>
        </b-input-group>
        <SidebarFilters />
        <b-button class="sidebar__btn sidebar__btn--remove" variant="light"
          >Remove All</b-button
        >
        <b-button class="sidebar__btn sidebar__btn--apply" variant="primary"
          >Apply</b-button
        >
      </div>
    </template>
  </b-sidebar>
</template>

<script>
import SidebarFilters from "./SidebarFilters.vue";
export default {
  name: "Drawer",
  props: ["width", "showBackdrop", "showRight"],
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

.search-box__button:hover,
.search-box__button:active {
  transform: scale(1.2);
}

.sidebar__close-btn.close {
  position: fixed;
  left: -3rem;
  top: 0;
  z-index: 1;
  background: $white;
  width: 3.5rem;
  height: 3.5rem;
  border-radius: 0 0 0 15px;
}

.b-sidebar.shadow.bg-light.text-dark {
  top: 3.5rem;
}

.b-sidebar.b-sidebar-right.bg-light.text-dark {
  left: 3rem;
  width: 91%;
  height: 100%;
  top: 0;
  z-index: 999999;
}

.sidebar__header {
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

.sidebar__search-box {
  margin: 2rem 0;
  outline: none;
}

.sidebar__rectangles__container {
  padding-right: 0;
  padding-left: 0;
}

.sidebar__rectangle {
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

.sidebar__btn {
  width: 7.8rem;
  height: 3rem;
  margin: 3%;
  font-weight: bold;
  border-radius: 1rem;
}

.sidebar__btn--remove {
  color: $blue;
  box-shadow: $shadow;
  background-color: $white;
}

.sidebar__btn--apply {
  color: $white;
  box-shadow: $shadow;
  background-color: $blue;
}
</style>
