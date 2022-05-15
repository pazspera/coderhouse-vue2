<template>
  <div class="row row-cols-1 row-cols-md-2 row-cols-lg-3 g-4">
    <div class="col" v-for="(product, p) in products" :key="p">
      <div class="card h-100" >
        <!-- <img :src="getImgUrl()" class="card-img-top" :alt="product.name" /> -->
        <div class="card-body">
          <h5 class="card-title">{{ product.name }}</h5>
          <p class="card-text">{{ product.description }}</p>
          <p class="card-text">${{ product.price }}</p>
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
  methods: {
    getImgUrl() {
      return require(`@/assets/img/${this.imgSrc}`);
    }
  }
};
</script>

<style></style>
