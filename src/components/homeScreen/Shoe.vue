<template>
  <b-container fluid class="shoe__card">
    <b-row align-h="end">
      <b-col cols="2" id="header__shoe-fit">
        99 <span class="header__shoe-fit-percent"> % </span></b-col
      >
      <b-col cols="10" class="header__order-options">
        <div class="header__online-group">
          <b-icon
            class="header__order-options__icon"
            icon="globe"
            id="asd"
          ></b-icon>
          <span class="header__online"> Online </span>
        </div>
        <div class="header__in-store-group">
          <b-icon
            class="header__order-options__icon"
            variant="success"
            icon="shop-window"
          ></b-icon>
          <span class="header__in-store"> In-store </span>
        </div>
      </b-col>
    </b-row>
    <b-row class="shoe__img__row">
      <b-img
        class="shoe__img"
        width="220px"
        src="../../assets/images/nike-shoe.png"
        fluid
        alt="Nike Shoe"
      ></b-img>
    </b-row>
    <b-row class="shoe__title" align-h="center" align-v="center">
      <span>{{ title }}</span>
    </b-row>
  </b-container>
</template>

<script>
export default {
  props: ["title"],
  name: "Shoe",
};
</script>

<style lang="scss">
.shoe__card {
  height: 17rem;
  max-width: 30rem;
  min-width: 21rem;
  margin: 0 0.5rem 1.5rem;
  border-radius: 1rem;
  box-shadow: 0 3px 22px 0 rgba(64, 64, 64, 0.1);
  background-color: $lightblue;
  overflow: hidden;
}

#header__shoe-fit {
  font-size: 1.2rem;
  font-weight: bold;
  color: #fff;
  padding-right: 2px;
  padding-top: 5px;
}

.header__shoe-fit-percent {
  font-size: 0.8rem;
  font-weight: 500;
}

.header__order-options {
  padding: 0.5rem 0;
  border-radius: 1.2rem 0 0 0;
  background: $white;
  justify-content: end;
  display: flex;
  flex-direction: row;
}

.header__online-group {
  color: $lightblue;
}

.header__online {
  text-align: left;
  margin: 0 0.2rem 0 0.2rem;
}

.header__in-store-group {
  margin: 0 0 0 1rem;
}

.header__in-store {
  font-size: 0.9rem;
  text-align: left;
  color: #27ae60;
  margin: 0 0.2rem 0 0.2rem;
}

.header__order-options__icon {
  display: inline;
}

.shoe__img__row {
  border-radius: 1.2rem 0 0 0;
  background: $white;
}

.shoe__img {
  width: 17rem;
  height: 8rem;
  margin: 1rem auto;
}

.shoe__title {
  font-size: 1.5rem;
  font-weight: 500;
  text-align: center;
  color: #404040;
  background: $white;
  padding-bottom: 100%;
}
</style>
