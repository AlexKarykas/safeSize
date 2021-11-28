<template>
  <div class="Background">
    <div class="card-header">
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
          <span class="Online"> Online </span>
        </div>
        <div class="in-store-group">
          <b-icon
            class="buy-group-icon"
            variant="success"
            icon="shop-window"
          ></b-icon>
          <span class="In-store"> In-store </span>
        </div>
      </div>
    </div>
    <div class="shoe">
      <b-img
        width="220px"
        src="../assets/images/nike-shoe.jpg"
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

<style>
.Background {
  width: 90%;
  height: 295px;
  margin: 0 12px 25px;
  border-radius: 17.4px;
  box-shadow: 0 3px 22px 0 rgba(64, 64, 64, 0.1);
  background-color: #fff;
  overflow: hidden;
}

.card-header {
  justify-content: space-between;
  display: flex;
  flex-direction: row;
}

.percentage-rectangle {
  text-align: center;
  padding-top: 2%;
  width: 15%;
  background-color: #3ea3dc;
  border-radius: 5%;
}

.order-options-group {
  margin: 3%;
  justify-content: space-between;
  display: flex;
  flex-direction: row;
}

.shoe-item_fit-number {
  font-size: 1rem;
  font-weight: bold;
  font-stretch: normal;
  font-style: normal;
  line-height: normal;
  letter-spacing: 0.5px;
  text-align: center;
  color: #fff;
}

.shoe-item_fit-percent {
  font-size: 12px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: normal;
  letter-spacing: 0.5px;
  text-align: center;
  color: #fff;
}

.shoe {
  display: block;
  top: 50%;
  left: 50%;
  width: 220px;
  height: 110px;
  margin: 2rem auto;
}

.Nike-Free-Run {
  font-size: 24px;
  font-weight: 500;
  font-stretch: normal;
  font-style: normal;
  line-height: normal;
  letter-spacing: 0.3px;
  text-align: center;
  color: #404040;
}

.online-group {
  justify-content: space-between;
  display: flex;
  flex-direction: row;
  width: 67.9px;
}

.Online {
  font-size: 14px;
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: normal;
  letter-spacing: normal;
  text-align: left;
  color: #3ea3dc;
}

.in-store-group {
  justify-content: space-between;
  display: flex;
  flex-direction: row;
  width: 73.9px;
  height: 17.3px;
  margin: 3px 0 0 15px;
}

.In-store {
  font-size: 14px;
  font-weight: normal;
  font-stretch: normal;
  font-style: normal;
  line-height: normal;
  letter-spacing: normal;
  text-align: left;
  color: #27ae60;
}

.buy-group-icon {
  display: inline;
}
</style>
