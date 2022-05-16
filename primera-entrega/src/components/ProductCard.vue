<template>
  <div class="col">
    <div class="card h-100">
      <img :src="getImgUrl(product.imgSrc)" class="card-img-top" :alt="product.name" />
      <div class="card-body">
        <h5 class="card-title">{{ product.name }}</h5>
        <p class="card-text">{{ product.description }}</p>
        <p class="card-text">${{ product.price }}</p>
        <ProductCounter @update-counter="addToCart" />
        <a href="#" @click.prevent="addToCart" :id="product.id" class="btn btn-primary">Agregar a carrito</a>
      </div>
    </div>
  </div>
</template>

<script>
import ProductCounter from "@/components/ProductCounter.vue";

export default {
  name: "ProductCard",
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
    addToCart(counter) {
      this.$emit("add-to-cart", this.product.id, counter);
      console.log(this.product.id);
      console.log(counter);
    },
  },
};
</script>

<style></style>
