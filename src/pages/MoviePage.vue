<template>
  <div class="product-page">
    <div class="product-filter q-ml-md q-mr-xl">
      <ProductFilter />
    </div>
    <div class="product-list q-mr-md">
      <ListMovie />
    </div>
  </div>
</template>
<style>
.product-page {
  display: flex;
  justify-content: space-between;
}

.product-filter {
  width: 25%;
}

.product-list {
  width: 75%;
}
</style>
<script>
import ListMovie from "src/components/movies/ListMovie.vue";

export default {
  name: "MoviePage",
  components: {
    ListMovie,
  },
};
</script>
