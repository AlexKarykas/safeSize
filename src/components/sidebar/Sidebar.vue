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
          @click="hide"
          class="d-inline-block d-sm-none sidebar__close-btn"
        ></b-button-close>
        <b-container>
          <b-row @click="hide" class="d-none d-sm-inline-block">
            <b-icon icon="chevron-left"></b-icon>
            <h2 class="sidebar__title">Our recommendations</h2>
          </b-row>
        </b-container>
        <FunctionalAdvice />
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
        <SidebarFilters v-bind:rightSidebar="showRight" />
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
import FunctionalAdvice from "./FunctionalAdvice.vue";

export default {
  name: "Sidebar",
  props: ["width", "showBackdrop", "showRight"],
  components: { SidebarFilters, FunctionalAdvice },
};
</script>

<style lang="scss">
.search-box,
.form-control.search-box,
.search-box:focus,
.form-control.search-box:focus {
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

.menu-header {
  padding: 0.25rem;
  font-size: 1.1rem;
  text-align: left;
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
  margin-left: 1rem;
  width: $b-sidebar-width;
}

.b-sidebar.b-sidebar-right.bg-light.text-dark {
  left: 3rem;
  width: 92%;
  height: 100%;
  top: 0;
  margin-left: 0;
  padding-right: 1rem;
  z-index: 999999;
}

.sidebar__title {
  display: inline-block;
  padding: 0.25rem;
  font-size: 1.3rem;
  text-align: left;
  &:hover {
    cursor: pointer;
  }
}

.sidebar-basic {
  padding: 1rem;
  min-width: 200px;
  justify-content: center;
}

.sidebar__search-box {
  margin: 2rem 0;
  outline: none;
}

.sidebar__btn {
  width: 7.8rem;
  height: 3rem;
  margin: 2%;
  font-weight: bold;
  border-radius: 1rem;
  box-shadow: $shadow;
}

.sidebar__btn--remove {
  color: $blue;
  background-color: $white;
}

.sidebar__btn--apply {
  color: $white;
  background-color: $blue;
}
</style>
