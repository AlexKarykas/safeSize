<template>
  <div class="accordion" role="tablist">
    <h4 class="menu-header">Filters</h4>
    <b-card no-body class="mb-1">
      <FilterHeader id="brand" header="Brand" :selected="selectedBrands" />
      <b-collapse id="brand" accordion="filters-accordion" role="tabpanel">
        <b-form-group class="brand-checkbox-list">
          <b-form-checkbox
            class="checkbox-item"
            v-for="(brand, value) in brands"
            :key="value"
            @change="addSelectedBrand($event)"
            :value="value"
            >{{ brand.description }}</b-form-checkbox
          >
        </b-form-group>
      </b-collapse>
    </b-card>
    <b-card no-body class="mb-1">
      <FilterHeader id="color" header="Colour" :selected="selectedColors" />
      <b-collapse id="color" accordion="filters-accordion" role="tabpanel">
        <b-button-group size="lg" class="color-btn-group">
          <b-button
            id="color-btn"
            v-bind:class="rightSidebar ? 'color-btn--sm' : 'color-btn--lg'"
            v-for="(btn, idx) in colorBtns"
            :key="idx"
            :pressed.sync="btn.state"
            variant="outline-secondary"
            @click="addSelectedColor"
          >
            {{ btn.caption }}
          </b-button>
        </b-button-group>
      </b-collapse>
    </b-card>
    <b-card no-body class="mb-1">
      <FilterHeader id="gender" header="Gender" />
      <b-collapse id="gender" accordion="filters-accordion" role="tabpanel">
        <b-form-group>Gender Options</b-form-group>
      </b-collapse>
    </b-card>
    <b-card no-body class="mb-1">
      <FilterHeader id="fabric" header="Fabric" />
      <b-collapse id="fabric" accordion="filters-accordion" role="tabpanel">
        <b-form-group>Fabric options</b-form-group>
      </b-collapse>
    </b-card>
    <b-card no-body class="mb-1">
      <FilterHeader id="availability" header="Availability" />
      <b-collapse
        id="availability"
        accordion="filters-accordion"
        role="tabpanel"
      >
        <b-form-group>Availability options</b-form-group>
      </b-collapse>
    </b-card>
  </div>
</template>

<script>
import FilterHeader from "./FilterHeader.vue";
export default {
  components: { FilterHeader },
  props: ["rightSidebar"],
  data() {
    return {
      myToggle: false,
      colorBtns: [
        { caption: "White", state: false },
        { caption: "Black", state: false },
        { caption: "Blue", state: false },
        { caption: "Grey", state: false },
        { caption: "Purple", state: false },
        { caption: "Green", state: false },
        { caption: "Brown", state: false },
        { caption: "Red", state: false },
        { caption: "Pink", state: false },
      ],
      brands: [
        { value: "NB", description: "New Balance" },
        { value: "Adidas", description: "Adidas" },
        { value: "NP", description: "Nike Performance" },
        { value: "Reebok", description: "Reebok" },
        { value: "Asics", description: "Asics" },
        { value: "UA", description: "Under Armour" },
        { value: "Puma", description: "Puma" },
      ],
      selectedBrands: 0,
      selectedColors: 0,
    };
  },
  methods: {
    addSelectedBrand(event) {
      if (event === false) {
        return this.selectedBrands--;
      }
      return this.selectedBrands++;
    },
    addSelectedColor(event) {
      if (event.target.classList.contains("active")) {
        return this.selectedColors--;
      }
      return this.selectedColors++;
    },
  },
  computed: {
    btnStates() {
      return this.colorBtns.map((btn) => btn.state);
    },
  },
};
</script>

<style lang="scss">
.btn-outline-secondary:not(:disabled):not(.disabled):active,
.btn-outline-secondary:not(:disabled):not(.disabled).active,
.show > .btn-outline-secondary.dropdown-toggle,
#color-btn:hover,
#color-btn:active {
  box-shadow: 3px 3px 3px 0 rgba(0, 0, 0, 0.16);
  background-color: $blue !important;
  color: $white !important;
}

.color-btn-group {
  text-align: left;
}

#color-btn {
  height: 3.2rem;
  font-size: 0.9rem;
  font-weight: 500;
  margin: 0.5rem;
  padding: 0;
  border-radius: 20%;
  color: #919698;
}

.color-btn--sm {
  width: 3.2rem;
}

.color-btn--lg {
  width: 4.4rem;
}

.brand-checkbox-list {
  text-align: left;
  margin-left: 2%;
}

.checkbox-item {
  margin: 1%;
}
</style>
