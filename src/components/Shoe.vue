<template>
  <div class="background">
    <b-container>
      <b-row align-h="between">
        <div class="percentage-rectangle">
          <span class="shoe-item_fit-number"> 99 </span>
          <span class="shoe-item_fit-percent"> % </span>
        </div>
        <div class="order-options-group">
          <div class="online-group">
            <b-icon
              class="buy-group-icon"
              variant="primary"
              icon="globe"
            ></b-icon>
            <span class="online"> Online </span>
          </div>
          <div class="in-store-group">
            <b-icon
              class="buy-group-icon"
              variant="success"
              icon="shop-window"
            ></b-icon>
            <span class="in-store"> In-store </span>
          </div>
        </div>
      </b-row>
    </b-container>
    <div class="shoe">
      <b-img
        width="220px"
        src="../assets/images/nike-shoe.png"
        fluid
        alt="Nike Shoe"
      ></b-img>
    </div>
    <div>
      <span class="Nike-Free-Run"> Nike Free Run </span>
    </div>
  </div>
</template>

<script>
export default {
  name: "Shoe",
};
</script>

<style lang="scss">
.background {
  height: 18rem;
  max-width: 29rem;
  margin: 0 0.5rem 1.5rem;
  border-radius: 1rem;
  box-shadow: 0 3px 22px 0 rgba(64, 64, 64, 0.1);
  background-color: #fff;
  overflow: hidden;
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

.shoe-item_fit-number {
  font-size: 1.2rem;
  font-weight: bold;
  text-align: center;
  color: #fff;
}

.shoe-item_fit-percent {
  font-size: 0.8rem;
  font-weight: 500;
  text-align: center;
  color: #fff;
}

.shoe {
  width: 13.7rem;
  height: 6.8rem;
  margin: 2rem auto;
  /* transform: rotateY(180deg); */
}

.Nike-Free-Run {
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

.buy-group-icon {
  display: inline;
}
</style>
