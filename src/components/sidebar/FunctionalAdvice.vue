<template>
  <b-container>
    <b-row align-h="between">
      <h4 class="menu-header">Functional Advice</h4>
      <b-form-checkbox switch size="lg" class="mr-n2"> </b-form-checkbox>
    </b-row>
    <b-row align-h="between" align-v="center" class="sidebar__rectangle">
      <p>CATEGORY: ROAD</p>
      <b-icon
        icon="info-circle-fill"
        variant="primary"
        v-b-tooltip.hover
        title="Ideal for Road Running"
      ></b-icon>
    </b-row>
    <b-row align-h="between" align-v="center" class="sidebar__rectangle">
      <p>CUSHIONING: CUSHIONING</p>
      <b-icon
        icon="info-circle-fill"
        variant="primary"
        v-b-tooltip.hover
        title="Cushioning for long distances"
      ></b-icon>
    </b-row>
    <b-row align-h="between" align-v="center" class="sidebar__rectangle">
      <p>STABILITY: STABLE+</p>
      <b-icon
        icon="info-circle-fill"
        variant="primary"
        v-b-tooltip.hover
        title="Most stable shoes"
      ></b-icon>
    </b-row>
  </b-container>
</template>

<script>
export default {
  name: "FunctionalAdvice",
  props: ["width", "showBackdrop", "showRight"],
};
</script>

<style lang="scss">
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
</style>
