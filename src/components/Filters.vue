<template>
  <div class="accordion" role="tablist">
    <h4 class="menu-header">Filters</h4>
    <b-card no-body class="mb-1">
      <b-card-header
        header-tag="header"
        class="
          p-1
          d-flex
          justify-content-between
          align-items-center
          filter-card-header
        "
        role="tab"
      >
        <a v-b-toggle.brand class="filters__toggle-header"
          >Brand &bull;
          <span class="items-selected">{{ selected }} selected</span></a
        >
        <a v-b-toggle.brand>
          <b-icon
            scale="1.5"
            class="when-closed"
            icon="chevron-down"
          ></b-icon>
          <b-icon
            scale="1.5"
            class="when-open"
            icon="chevron-up"
          ></b-icon
        ></a>
      </b-card-header>
      <b-collapse id="brand" accordion="my-accordion" role="tabpanel">
        <b-form-group class="brand-checkbox-list">
          <b-form-checkbox
            class="checkbox-item"
            @change="addSelectedBrand($event)"
            value="NB"
            >New Balance</b-form-checkbox
          >
          <b-form-checkbox
            class="checkbox-item"
            @change="addSelectedBrand($event)"
            value="Adidas"
            >Adidas</b-form-checkbox
          >
          <b-form-checkbox
            class="checkbox-item"
            @change="addSelectedBrand($event)"
            value="Nike"
            >Nike Performance</b-form-checkbox
          >
          <b-form-checkbox
            class="checkbox-item"
            @change="addSelectedBrand($event)"
            value="Reebok"
            >Reebok</b-form-checkbox
          >
          <b-form-checkbox
            class="checkbox-item"
            @change="addSelectedBrand($event)"
            value="Asics"
            >Asics</b-form-checkbox
          >
          <b-form-checkbox
            class="checkbox-item"
            @change="addSelectedBrand($event)"
            value="UA"
            >Under Armour</b-form-checkbox
          >
          <b-form-checkbox
            class="checkbox-item"
            @change="addSelectedBrand($event)"
            value="Puma"
            >Puma</b-form-checkbox
          >
        </b-form-group>
      </b-collapse>
    </b-card>
    <b-card no-body class="mb-1">
      <b-card-header
        header-tag="header"
        class="
          p-1
          d-flex
          justify-content-between
          align-items-center
          filter-card-header
        "
        role="tab"
      >
        <a v-b-toggle.color class="filters__toggle-header">Colour </a>
        <a v-b-toggle.color>
          <b-icon
            scale="1.5"
            class="when-closed"
            icon="chevron-down"
          ></b-icon>
          <b-icon
            scale="1.5"
            class="when-open"
            icon="chevron-up"
          ></b-icon
        ></a>
      </b-card-header>
      <b-collapse id="color" accordion="my-accordion" role="tabpanel">
        <b-button-group size="sm" class="color-btn-goup">
          <b-button
            class="color-btn"
            v-for="(btn, idx) in colorBtns"
            :key="idx"
            :pressed.sync="btn.state"
            variant="outline-secondary"
          >
            {{ btn.caption }}
          </b-button>
        </b-button-group>
      </b-collapse>
    </b-card>
    <b-card no-body class="mb-1">
      <b-card-header
        header-tag="header"
        class="
          p-1
          d-flex
          justify-content-between
          align-items-center
          filter-card-header
        "
        role="tab"
      >
        <a v-b-toggle.gender class="filters__toggle-header">Gender</a>
        <a v-b-toggle.gender>
          <b-icon
            scale="1.5"
            class="when-closed"
            icon="chevron-down"
          ></b-icon>
          <b-icon
            scale="1.5"
            class="when-open"
            icon="chevron-up"
          ></b-icon
        ></a>
      </b-card-header>
      <b-collapse id="gender" accordion="my-accordion" role="tabpanel">
        <b-form-group> </b-form-group>
      </b-collapse>
    </b-card>
    <b-card no-body class="mb-1">
      <b-card-header
        header-tag="header"
        class="
          p-1
          d-flex
          justify-content-between
          align-items-center
          filter-card-header
        "
        role="tab"
      >
        <a v-b-toggle.fabric class="filters__toggle-header"> Fabric</a>
        <a v-b-toggle.fabric>
          <b-icon
            scale="1.5"
            class="when-closed"
            icon="chevron-down"
          ></b-icon>
          <b-icon
            scale="1.5"
            class="when-open"
            icon="chevron-up"
          ></b-icon>
        </a>
      </b-card-header>
      <b-collapse id="fabric" accordion="my-accordion" role="tabpanel">
        <b-form-group> </b-form-group>
      </b-collapse>
    </b-card>
    <b-card no-body class="mb-1">
      <b-card-header
        header-tag="header"
        class="
          p-1
          d-flex
          justify-content-between
          align-items-center
          filter-card-header
        "
        role="tab"
      >
        <a v-b-toggle.availability class="filters__toggle-header">
          Availability</a
        >
        <a v-b-toggle.availability>
          <b-icon
            scale="1.5"
            class="when-closed"
            icon="chevron-down"
          ></b-icon>
          <b-icon
            scale="1.5"
            class="when-open"
            icon="chevron-up"
          ></b-icon>
        </a>
      </b-card-header>
      <b-collapse id="availability" accordion="my-accordion" role="tabpanel">
        <b-form-group> </b-form-group>
      </b-collapse>
    </b-card>
  </div>
</template>

<script>
export default {
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
      selected: 0,
    };
  },
  methods: {
    addSelectedBrand(event) {
      if (!event) {
        return this.selected--;
      }
      return this.selected++;
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
.collapsed > .when-open,
.not-collapsed > .when-closed {
  display: none;
}

.btn-outline-secondary:not(:disabled):not(.disabled):active,
.btn-outline-secondary:not(:disabled):not(.disabled).active,
.show > .btn-outline-secondary.dropdown-toggle,
.color-btn:hover {
  box-shadow: 0 3px 3px 0 rgba(0, 0, 0, 0.16);
  border: solid 1px $blue;
  background-color: $blue;
}

.items-selected {
  color: $blue;
  font-weight: bold;
}

.color-btn-goup {
  text-align: left;
}

.brand-checkbox-list {
  text-align: left;
  margin-left: 2%;
}

.checkbox-item {
  margin: 1%;
}

.menu-header {
  padding: 0.25rem;
  font-size: 1.1rem;
  text-align: left;
}

.filter-card-header {
  border-bottom: 1px solid $gray-border;
}

.color-btn {
  width: 3.2rem;
  height: 3.2rem;
  align-items: center;
  font-size: 0.9rem;
  font-weight: 500;
  margin: 0.5rem;
  padding: 0;
  border-radius: 25%;
}

a:hover {
  text-decoration: none;
}
.filters__toggle-header {
  text-decoration: none;
  font-size: 0.9rem;
  font-weight: 500;
  letter-spacing: 0.5px;
  color: #404040;
}
</style>
