<template>
  <main id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
    <section class="container my-5">
      <h2 class="mb-3">Hamburguesas</h2>
      <ProductCard :products="products.hamburgers" />
    </section>

    <section class="container my-5">
      <h2 class="mb-3">Tapas</h2>
      <ProductCard :products="products.tapas" />
    </section>

    <section class="container my-5">
      <h2 class="mb-3">Bebidas</h2>
      <ProductCard :products="products.drinks" />
    </section>
  </main>
</template>

<script>
import axios from "axios";
import ProductCard from "@/components/ProductCard.vue";

export default {
  name: "App",
  components: {
    ProductCard,
  },
  data: () => ({
    products: [],
    cart: []
  }),
  mounted() {
    this.getProducts();
  },
  methods: {
    async getProducts() {
      try {
        const res = await axios.get("./data/products.json");
        // Guarda lo que se recibe en el products del data
        this.products = await res.data;
      } catch (error) {
        console.log(error);
      }
    }
  }
};
</script>

<style>
#app {
  margin: 0;
}
</style>
