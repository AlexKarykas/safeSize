<template>
  <b-container fluid class="shoe__card">
    <b-row align-h="between">
      <div class="percentage-rectangle">
        <span class="shoe__fit-number"> 99 </span>
        <span class="shoe__fit-percent"> % </span>
      </div>
      <div class="order-options-group">
        <div class="online-group">
          <b-icon
            class="order-options__icon"
            variant="primary"
            icon="globe"
          ></b-icon>
          <span class="online"> Online </span>
        </div>
        <div class="in-store-group">
          <b-icon
            class="order-options__icon"
            variant="success"
            icon="shop-window"
          ></b-icon>
          <span class="in-store"> In-store </span>
        </div>
      </div>
    </b-row>
    <b-row>
      <div class="shoe__img">
        <b-img
          width="220px"
          src="../assets/images/nike-shoe.png"
          fluid
          alt="Nike Shoe"
        ></b-img>
      </div>
    </b-row>
    <b-row align-h="center" align-v="center">
      <span class="shoe__title">{{ title }}</span>
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
  height: 18rem;
  max-width: 29rem;
  min-width: 21rem;
  margin: 0 0.5rem 1.5rem;
  border-radius: 1rem;
  box-shadow: 0 3px 22px 0 rgba(64, 64, 64, 0.1);
  background-color: #fff;
  overflow: hidden;
  z-index: -1;
}

.percentage-rectangle {
  padding-top: 2%;
  width: 15%;
  background-color: $lightblue;
  border-radius: 5%;
}

.order-options-group {
  margin: 3%;
  justify-content: space-between;
  display: flex;
  flex-direction: row;
}

.shoe__fit-number {
  font-size: 1.2rem;
  font-weight: bold;
  text-align: center;
  color: #fff;
}

.shoe__fit-percent {
  font-size: 0.8rem;
  font-weight: 500;
  text-align: center;
  color: #fff;
}

.shoe__img {
  width: 13.7rem;
  height: 6.8rem;
  margin: 2rem auto;
}

.shoe__title {
  font-size: 1.5rem;
  font-weight: 500;
  text-align: center;
  color: #404040;
}

.online-group {
  justify-content: space-between;
  display: flex;
  flex-direction: row;
  width: 4rem;
  height: 1rem;
}

.online {
  font-size: 0.9rem;
  text-align: left;
  color: $lightblue;
}

.in-store-group {
  justify-content: space-between;
  display: flex;
  flex-direction: row;
  width: 5rem;
  height: 1rem;
  margin: 0 0 0 1rem;
}

.in-store {
  font-size: 0.9rem;
  text-align: left;
  color: #27ae60;
}

.order-options__icon {
  display: inline;
}
</style>
