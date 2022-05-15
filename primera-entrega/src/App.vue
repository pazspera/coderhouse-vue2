<template>
  <main id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
    <section class="container my-5">
      <h2 class="mb-3">Hamburguesas</h2>
      <ProductCard :products="hamburgers" />
    </section>

    <section class="container my-5">
      <h2 class="mb-3">Tapas</h2>
      <ProductCard :products="tapas" />
    </section>

    <section class="container my-5">
      <h2 class="mb-3">Bebidas</h2>
      <ProductCard :products="drinks" />
    </section>
  </main>
</template>

<script>
import ProductCard from "@/components/ProductCard.vue";

export default {
  name: "App",
  components: {
    ProductCard,
  },
  mounted() {
    // a la carga del documento se dividen los datos de products en categorías, 
    // así se pueden mostrar en el DOM en base a cada categoría
    this.hamburgers = this.filterProducts(this.products, "hamburgers");
    this.tapas = this.filterProducts(this.products, "tapas");
    this.drinks = this.filterProducts(this.products, "drinks");
  },
  data() {
    return {
      products: [
        {
          id: "h01",
          name: "Doble Bacon",
          description: "2 medallones de carne de 100gr, cheddar, panceta ahumada, cebolla caramelizada",
          price: "1120",
          imgSrc: "doble_bacon.jpg",
          category: "hamburgers",
        },
        {
          id: "h02",
          name: "Baby Blue",
          description: "Medallón de carne de 100gr, queso azul, morrón, cebolla caramelizada, pepinillos",
          price: "1050",
          imgSrc: "baby_blue.jpg",
          category: "hamburgers",
        },
        {
          id: "h03",
          name: "Locura Not Burger",
          description: "Medallón not burger, guacamole, tomate, cebolla caramelizada, huevo frito",
          price: "1050",
          imgSrc: "locura_not_burger.jpg",
          category: "hamburgers",
        },
        {
          id: "h04",
          name: "Remolacha Pasión",
          description: "Medallón de remolacha, tomates cherry, mozzarella",
          price: "950",
          imgSrc: "remolacha_pasion.jpg",
          category: "hamburgers",
        },
        {
          id: "t01",
          name: "Papas con Cheddar",
          description: "Papas fritas con salsa cheddar",
          price: "550",
          imgSrc: "papas_cheddar.jpg",
          category: "tapas",
        },
        {
          id: "t02",
          name: "Papas Bravas",
          description: "Papas fritas con salsa picante",
          price: "550",
          imgSrc: "papas_bravas.jpg",
          category: "tapas",
        },
        {
          id: "t03",
          name: "Nachos Completos",
          description: "Nachos con queso cheddar y dip de guacamole",
          price: "750",
          imgSrc: "nachos_completos.jpg",
          category: "tapas",
        },
        {
          id: "t04",
          name: "Mozzarellas Pasión",
          description: "Triángulos de queso mozzarella rebozados (6) con salsa de toma y guacamole",
          price: "950",
          imgSrc: "mozzarellas_pasion.jpg",
          category: "tapas",
        },
        {
          id: "d01",
          name: "Coca Cola Lata 354ml",
          price: "250",
          imgSrc: "coca_cola_354.jpg",
          category: "drinks",
        },
        {
          id: "d02",
          name: "Sprite Lata 354ml",
          price: "250",
          imgSrc: "sprite_354.jpg",
          category: "drinks",
        },
        {
          id: "d03",
          name: "Agua Botella 500ml",
          price: "250",
          imgSrc: "agua_500.jpg",
          category: "drinks",
        },
        {
          id: "d04",
          name: "Porrón Patagonia 500ml",
          price: "450",
          imgSrc: "porron_patagonia_500.jpg",
          category: "drinks",
        },
        {
          id: "d05",
          name: "Botella Patagonia 1 litro",
          price: "950",
          imgSrc: "patagonia_1litro.jpg",
          category: "drinks",
        },
      ],
      hamburgers: [],
      tapas: [],
      drinks: [],
      cart: []
    };
  },
  methods: {
    filterProducts(array, category) {
      // recibe todos los productos y, en base a la categoría de producto, se guarda
      // en un array por categoría (hamburgers, tapas, drinks)
      let filteredArray = array.filter((product) => product.category === category);
      return filteredArray;
    },
  },
};
</script>

<style>
#app {
  margin: 0;
}
</style>
