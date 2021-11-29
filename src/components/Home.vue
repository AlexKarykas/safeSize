<template>
  <div class="home">
    <span class="recommendation"> Our recommendation </span>
    <b-container fluid="l">
      <b-row>
        <b-col><Shoe /></b-col>
        <b-col><Shoe /></b-col>
        <b-col><Shoe /></b-col>
      </b-row>
      <b-row>
        <b-col><Shoe /></b-col>
        <b-col><Shoe /></b-col>
        <b-col><Shoe /></b-col>
      </b-row>
      <b-row>
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

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.recommendation {
  margin: 5%;
  font-size: 1.5rem;
  font-weight: 500;
  letter-spacing: 0.15px;
  color: #404040;
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
