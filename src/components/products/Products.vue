<template>
  <div class="container">
    <div class="row">
      <div class="left-content"></div>
      <div class="products">
        <div class="hat-section">
          <h2>HATS</h2>
          <div class="hat-col">I"m okaty</div>
          <div class="hat-col">I"m okaty</div>
          <div class="hat-col">I"m okaty</div>
          <div class="hat-col">I"m okaty</div>
        </div>
      </div>
      <div class="right-content"></div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "Products",
  data() {
    return {
      keyword: "fun",
      hatData: [],
      Key: "wK73rU3NtfyGz4_8kTr1Ezb_HxwN12slteA8Giz8mks",
      page: 1,
      per_page: 4,
      url: `https://api.unsplash.com/search/photos?page=${this.page}&per_page=${this.per_page}&client_id=${this.Key}&query=`,
    };
  },
  methods: {},
  mounted() {
    axios
      .get(this.url + this.keyword)
      .then((response) => (this.hatData = response))
      .catch((err) => err);
    console.log(this.page);
  },
};
</script>

<style scoped>
.container {
  /* display: flex; */
  /* justify-content: center; */
  /* width: 70% !important; */
  background-color: aquamarine;
}
.row {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}

.left-content {
  flex-basis: 10%;
}
.right-content {
  flex-basis: 10%;
}
.products {
  flex-basis: 80%;
}
.hat-section {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  /* justify-content: center; */
  /* justify-content: space-between; */
  /* width: 60%; */

  justify-content: space-between;
}
</style>>

