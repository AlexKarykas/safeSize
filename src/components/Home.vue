<template>
  <div class="home">
    <span class="title-sm d-block d-sm-none"> Our recommendation </span>
    <span class="title-lg d-none d-sm-block"> 15 RESULTS </span>
    <b-container fluid="l" class="shoes-container">
      <b-row no-gutters>
        <b-col><Shoe /></b-col>
        <b-col><Shoe /></b-col>
        <b-col><Shoe /></b-col>
      </b-row>
      <b-row no-gutters>
        <b-col><Shoe /></b-col>
        <b-col><Shoe /></b-col>
        <b-col><Shoe /></b-col>
      </b-row>
      <b-row no-gutters>
        <b-col><Shoe /></b-col>
        <b-col><Shoe /></b-col>
        <b-col><Shoe /></b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import Shoe from "./Shoe.vue";
export default {
  name: "Home",
  components: {
    Shoe,
  },
  props: {
    msg: String,
  },
};
</script>

<style >
.home,
.shoes-container {
  margin-top: 1rem;
}

.title-sm,
.title-lg {
  padding: 1rem;
  font-size: 1.5rem;
  font-weight: 500;
  letter-spacing: 0.15px;
  color: #404040;
}

.title-lg {
	text-align: left;
}
</style>
