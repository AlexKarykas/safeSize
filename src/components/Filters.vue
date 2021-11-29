<template>
  <div class="accordion filter-area" role="tablist">
    <h4 class="filters-header">Filters</h4>
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
        <a v-b-toggle.brand class="filter-header-text"
          >Brand <strong>{{ selected }}1 selected</strong></a
        >
        <a v-b-toggle.brand>
          <b-icon
            scale="1.5"
            class="when-closed"
            icon="chevron-compact-down"
          ></b-icon>
          <b-icon
            scale="1.5"
            class="when-open"
            icon="chevron-compact-up"
          ></b-icon
        ></a>
      </b-card-header>
      <b-collapse id="brand" accordion="my-accordion" role="tabpanel">
        <b-form-group class="brand-checkbox-list">
          <b-form-checkbox class="checkbox-item" value="NB"
            >New Balance</b-form-checkbox
          >
          <b-form-checkbox class="checkbox-item" value="Adidas"
            >Adidas</b-form-checkbox
          >
          <b-form-checkbox class="checkbox-item" value="Nike"
            >Nike Performance</b-form-checkbox
          >
          <b-form-checkbox class="checkbox-item" value="Reebok"
            >Reebok</b-form-checkbox
          >
          <b-form-checkbox class="checkbox-item" value="Asics"
            >Asics</b-form-checkbox
          >
          <b-form-checkbox class="checkbox-item" value="UA"
            >Under Armour</b-form-checkbox
          >
          <b-form-checkbox class="checkbox-item" value="Puma"
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
        <a v-b-toggle.color class="filter-header-text">Colour </a>
        <a v-b-toggle.color>
          <b-icon
            scale="1.5"
            class="when-closed"
            icon="chevron-compact-down"
          ></b-icon>
          <b-icon
            scale="1.5"
            class="when-open"
            icon="chevron-compact-up"
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
        <a v-b-toggle.gender class="filter-header-text">Gender</a>
        <a v-b-toggle.gender>
          <b-icon
            scale="1.5"
            class="when-closed"
            icon="chevron-compact-down"
          ></b-icon>
          <b-icon
            scale="1.5"
            class="when-open"
            icon="chevron-compact-up"
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
        <a v-b-toggle.fabric class="filter-header-text"> Fabric</a>
        <a v-b-toggle.fabric>
          <b-icon
            scale="1.5"
            class="when-closed"
            icon="chevron-compact-down"
          ></b-icon>
          <b-icon
            scale="1.5"
            class="when-open"
            icon="chevron-compact-up"
          ></b-icon>
        </a>
      </b-card-header>
      <b-collapse id="fabric" accordion="my-accordion" role="tabpanel">
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
    };
  },
  computed: {
    btnStates() {
      return this.colorBtns.map((btn) => btn.state);
    },
  },
};
</script>

<style>
.collapsed > .when-open,
.not-collapsed > .when-closed {
  display: none;
}

.btn-outline-secondary:not(:disabled):not(.disabled):active,
.btn-outline-secondary:not(:disabled):not(.disabled).active,
.show > .btn-outline-secondary.dropdown-toggle,
.color-btn:hover {
  box-shadow: 0 3px 3px 0 rgba(0, 0, 0, 0.16);
  border: solid 1px #006eb7;
  background-color: #006eb7;
}

.filter-area {
	margin: 1rem;
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

.filters-header {
  padding: 0.25rem;
  font-size: 1.2rem;
  text-align: left;
}

.filter-card-header {
  border-bottom: 1px solid #e7e7e7;
}

.color-btn {
  width: 3.8rem;
  height: 3.8rem;
  align-items: center;
  margin: 10px;
  padding: 0;
}

a:hover {
  text-decoration: none;
}
.filter-header-text {
  text-decoration: none;
  font-size: 1rem;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: normal;
  letter-spacing: 0.5px;
  color: #404040;
}

.filter-selected {
  font-size: 12px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: normal;
  letter-spacing: 0.5px;
  text-align: left;
  color: #006eb7;
  border-bottom: 1px solid black;
}
</style>
