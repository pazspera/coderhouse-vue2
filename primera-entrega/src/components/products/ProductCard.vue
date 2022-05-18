<template>
  <div class="col">
    <div class="card h-100">
      <img :src="getImgUrl(product.imgSrc)" class="card-img-top" :alt="product.name" />
      <div class="card-body">
        <h5 class="card-title">{{ product.name }}</h5>
        <p class="card-text">{{ product.description }}</p>
        <p class="card-text">${{ product.price }}</p>
        <ProductCounter @update-counter="updateCounter" />
        <button type="button" @click.prevent="addToCart" :id="product.id" class="btn btn-primary">Agregar a carrito</button>
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

<style lang="scss" scoped>
@import "@/assets/scss/main.scss";

.card,
.card img {
  border-radius: 0;
}

.card {
  border-bottom-color: $secondary;
  border-left-color: $secondary;
  border-right-color: $secondary;
  border-top-color: $secondary;
}

.card-title {
  font-size: $size4;
}

.card-text {
  font-size: $size6;
  font-weight: 500;
}

.card-body{
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.btn {
  border-radius: 0;
  text-transform: uppercase;
  width: 100%;
  font-weight: 600;
  background-color: $primary;
  border-bottom-color: $primary;
  border-left-color: $primary;
  border-right-color: $primary;
  border-top-color: $primary;
}

.btn:hover,
.btn-primary:hover {
  background-color: $black;
  border-bottom-color: $black;
  border-left-color: $black;
  border-right-color: $black;
  border-top-color: $black;
}

.btn-primary:active {
  background-color: $black;
  border-color: $black;
}

.btn-primary:active:focus,
.btn-primary:active:focus-within {
  box-shadow: none;
  background-color: $black;
  border-color: $black;
}

button:focus {
  outline: none;
  box-shadow: none;
  background-color: $black;
  border-color: $black;
}

button:focus-visible {
  outline: none;
  box-shadow: none;
  background-color: $black;
  border-color: $black;
}
</style>
