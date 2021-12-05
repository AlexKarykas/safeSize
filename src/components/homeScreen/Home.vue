<template>
  <div>
    <span class="home__title--sm d-block d-sm-none"> Our recommendation </span>
    <span class="home__title--lg d-none d-sm-block">
      {{ results.length }} RESULTS
    </span>
    <b-container fluid >
      <b-row align-v="start">
        <b-col v-for="(shoe, idx) in results" :key="idx">
          <Shoe :title="shoe.title"
        /></b-col>
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
  data() {
    return {
      results: [
        //Items fetched from an HTTP request
        { id: 1, title: "Nike Free Run" },
        { id: 2, title: "Nike Free Run" },
        { id: 3, title: "Nike Free Run" },
        { id: 4, title: "Nike Free Run" },
        { id: 5, title: "Nike Free Run" },
        { id: 6, title: "Nike Free Run" },
        { id: 7, title: "Nike Free Run" },
        { id: 8, title: "Nike Free Run" },
        { id: 9, title: "Nike Free Run" },
        { id: 10, title: "Nike Free Run" },
        { id: 11, title: "Nike Free Run" },
        { id: 12, title: "Nike Free Run" },
        { id: 13, title: "Nike Free Run" },
        { id: 14, title: "Nike Free Run" },
        { id: 15, title: "Nike Free Run" },
      ],
    };
  },
};
</script>

<style >
.home__title--sm,
.home__title--lg {
  padding: 1rem;
  font-size: 1.3rem;
  font-weight: 500;
  letter-spacing: 0.15px;
  color: #404040;
}

.home__title--lg {
  text-align: left;
}
</style>
