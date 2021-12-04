<template>
  <b-card-header
    header-tag="header"
    class="
      p-1
      d-flex
      justify-content-between
      align-items-center
      filters__card__header
    "
    role="tab"
  >
    <a v-b-toggle="id" class="filter__header"
      >{{ header }} <span v-if="selected"> &bull; </span>
      <span v-if="selected" class="filter__header__items-selected"
        >{{ selected }} selected</span
      ></a
    >
    <a v-b-toggle="id">
      <b-icon scale="1.5" class="when-closed" icon="chevron-down"></b-icon>
      <b-icon scale="1.5" class="when-open" icon="chevron-up"></b-icon
    ></a>
  </b-card-header>
</template>

<script>
export default {
  name: "FilterHeader",
  props: ["header", "id", "selected"],
};
</script>

<style lang="scss">
a:hover {
  text-decoration: none;
}
.filters__card__header {
  border-bottom: 1px solid $gray-border;
}

.filter__header {
  text-decoration: none;
  font-size: 0.9rem;
  font-weight: 500;
  letter-spacing: 0.5px;
  color: #404040;
  &:hover {
    cursor: pointer;
  }
}

.filter__header__items-selected {
  color: $blue;
  font-weight: bold;
}

.collapsed > .when-open,
.not-collapsed > .when-closed {
  display: none;
}
</style>