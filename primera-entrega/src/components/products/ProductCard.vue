<template>
  <div class="col">
    <div class="card h-100">
      <img :src="getImgUrl(product.imgSrc)" class="card-img-top" :alt="product.name" />
      <div class="card-body">
        <h5 class="card-title">{{ product.name }}</h5>
        <p class="card-text">{{ product.description }}</p>
        <p class="card-text">${{ product.price }}</p>
        <ProductCounter @update-counter="updateCounter" />
        <a href="#" @click.prevent="addToCart" :id="product.id" class="btn btn-primary">Agregar a carrito</a>
      </div>
    </div>
  </div>
</template>

<script>
import ProductCounter from "@/components/products/ProductCounter.vue";

export default {
  name: "ProductCard",
  data() {
    return {
      productCounter: 1,
    };
  },
  components: {
    ProductCounter,
  },
  props: {
    product: {
      type: Object,
      required: true,
    },
  },
  methods: {
    // Las imgs no estaban funcionando hasta que agregué que en el template getImgUrl reciba como
    // parámetro el imgSrc de cada producto y lo agregué al final de la ruta
    getImgUrl(imgSrc) {
      return require("@/assets/img/" + imgSrc);
    },
    addToCart() {
      this.$emit("add-to-cart", {
        productId: this.product.id,
        productCounter: this.productCounter,
      });
    },
    updateCounter(counter) {
      this.productCounter = counter;
    },
  },
};
</script>

<style></style>
