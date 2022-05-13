<template>
  <div class="row">
    <div class="col sm-6 lg-4" v-for="(product, p) in products" :key="p">
      <div class="card h-100" >
        <!-- <img src="..." class="card-img-top" alt="..." /> -->
        <div class="card-body">
          <h5 class="card-title">{{ product.name }}</h5>
          <p class="card-text">{{ product.description }}</p>
          <p class="card-text">{{ product.price }}</p>
          <a href="#" class="btn btn-primary">Agregar a carrito</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProductCard",
  props: {
    products: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style></style>
