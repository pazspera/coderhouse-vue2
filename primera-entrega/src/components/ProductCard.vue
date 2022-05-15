<template>
  <div class="row row-cols-1 row-cols-md-2 row-cols-lg-3 g-4">
    <div class="col" v-for="product in products" :key="product.id">
      <div class="card h-100">
        <img :src="getImgUrl(product.imgSrc)" class="card-img-top" :alt="product.name" />
        <div class="card-body">
          <h5 class="card-title">{{ product.name }}</h5>
          <p class="card-text">{{ product.description }}</p>
          <p class="card-text">${{ product.price }}</p>
          <a href="#" @click="addToCart" :id="product.id" class="btn btn-primary">Agregar a carrito</a>
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
    // Las imgs no estaban funcionando hasta que agregué que en el template getImgUrl reciba como
    // parámetro el imgSrc de cada producto y lo agregué al final de la ruta
    getImgUrl(imgSrc) {
      return require("@/assets/img/" + imgSrc);
    },
    addToCart(){
      // Estoy tratando de que al hacer click en el btn de la card, que imprima en consola 
      // el product.id. Me devuelve undefined y no entiendo porqué
      console.log(this.product.id);
    }
  },
};
</script>

<style></style>
