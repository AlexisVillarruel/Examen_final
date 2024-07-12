<template>
  <q-card class="product-card">
    <q-card-section>
      <q-img :src="movie.poster_path" alt="Imagen de la pelicula" />
    </q-card-section>
    <q-card-section>
      <q-card-title>{{ movie.title }}</q-card-title>
      <div class="text-h6 font-weight-bold">
        {{ movie.vote_average }}
      </div>
      <div class="text-center">
        <q-btn color="primary" icon="add_shopping_cart" label="Agregar"></q-btn>
      </div>
    </q-card-section>
  </q-card>
</template>

<style>
.product-card {
  width: 300px;
}
.product-card q-card-section {
  height: 100px;
  overflow: hidden;
}
</style>

<script>
export default {
  name: "ItemMovie",
  props: {
    movie: {
      type: Object,
      required: true,
    },
  },
};
</script>
