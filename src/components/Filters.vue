<template>
  <div class="accordion" role="tablist">
    <b-card no-body class="mb-1">
      <b-card-header header-tag="header" class="p-1" role="tab">
        <a v-b-toggle.brand class="filter-header-text"
          >Brand
          <strong>{{ selected }} selected</strong>
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
      <b-card-header header-tag="header" class="p-1" role="tab">
        <a v-b-toggle.color class="filter-header-text"
          >Colour
          <b-icon class="when-closed" icon="chevron-compact-down"></b-icon>
          <b-icon class="when-open" icon="chevron-compact-up"></b-icon
        ></a>
      </b-card-header>
      <b-collapse id="color" accordion="my-accordion" role="tabpanel">
        <b-form-group>
          <b-container fluid="l">
            <b-row>
              <b-col
                ><b-button class="color-btn" variant="light"
                  >White</b-button
                ></b-col
              >
              <b-col
                ><b-button class="color-btn" variant="light"
                  >Black</b-button
                ></b-col
              >
              <b-col
                ><b-button class="color-btn" variant="light"
                  >Blue</b-button
                ></b-col
              >
              <b-col
                ><b-button class="color-btn" variant="light"
                  >Grey</b-button
                ></b-col
              >
              <b-col
                ><b-button class="color-btn" variant="light"
                  >Purple</b-button
                ></b-col
              >
              <b-col
                ><b-button class="color-btn" variant="light"
                  >Green</b-button
                ></b-col
              >
              <b-col
                ><b-button class="color-btn" variant="light"
                  >Brown</b-button
                ></b-col
              >
              <b-col
                ><b-button class="color-btn" variant="light"
                  >Red</b-button
                ></b-col
              >
              <b-col
                ><b-button class="color-btn" variant="light"
                  >Pink</b-button
                ></b-col
              >
            </b-row>
          </b-container>
          <div class="MobileFilterActive">Blue</div>
          <div class="MobileFilterInactive">White</div>
        </b-form-group>
      </b-collapse>
    </b-card>
    <b-card no-body class="mb-1">
      <b-card-header header-tag="header" class="p-1" role="tab">
        <a v-b-toggle.gender class="filter-header-text"
          >Gender
          <b-icon class="when-closed" icon="chevron-compact-down"></b-icon>
          <b-icon class="when-open" icon="chevron-compact-up"></b-icon
        ></a>
      </b-card-header>
      <b-collapse id="gender" accordion="my-accordion" role="tabpanel">
        <b-form-group> </b-form-group>
      </b-collapse>
    </b-card>
    <b-card no-body class="mb-1">
      <b-card-header header-tag="header" class="p-1" role="tab">
        <a v-b-toggle.fabric class="filter-header-text"
          >Fabric
          <b-icon class="when-closed" icon="chevron-compact-down"></b-icon>
          <b-icon class="when-open" icon="chevron-compact-up"></b-icon
        ></a>
      </b-card-header>
      <b-collapse id="fabric" accordion="my-accordion" role="tabpanel">
        <b-form-group> </b-form-group>
      </b-collapse>
    </b-card>
  </div>
</template>

<script>
export default {};
</script>

<style>
.collapsed > .when-open,
.not-collapsed > .when-closed {
  display: none;
}

.brand-checkbox-list {
  text-align: left;
  margin-left: 2%;
}

.checkbox-item {
  margin: 1%;
}

.color-btn {
  border-radius: 15px;
  box-shadow: 0 3px 3px 0 rgba(0, 0, 0, 0.16);
  border: solid 1px rgba(145, 150, 152, 0.6);
  background-color: #fff;
}

.MobileFilterActive {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  gap: 10px;
  margin: 0 20px 0 0;
  padding: 10px 16px;
  border-radius: 15px;
  box-shadow: 0 3px 3px 0 rgba(0, 0, 0, 0.16);
  border: solid 1px #006eb7;
  background-color: #006eb7;
}
.MobileFilterInactive {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  gap: 10px;
  margin: 0 0 0 20px;
  padding: 10px 16px;
  border-radius: 15px;
  box-shadow: 0 3px 3px 0 rgba(0, 0, 0, 0.16);
  border: solid 1px rgba(145, 150, 152, 0.6);
  background-color: #fff;
}
a:hover {
  text-decoration: none;
}
.filter-header-text {
  text-decoration: none;
  font-size: 12px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: normal;
  letter-spacing: 0.5px;
  text-align: left;
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
}
</style>
