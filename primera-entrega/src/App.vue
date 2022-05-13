<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <ProductCard  v-for="(product, p) in products" :key="p"  />
  </div>
</template>

<script>
import ProductCard from "./components/ProductCard.vue";

export default {
  name: "App",
  components: {
    ProductCard,
  },
  data() {
    return {
      hamburgers: {
        products: [
          {
            name: "Doble Bacon",
            description: "2 medallones de carne de 100gr, cheddar, panceta ahumada, cebolla caramelizada",
            price: "1120",
          },
          {
            name: "Baby Blue",
            description: "Medallón de carne de 100gr, queso azul, morrón, cebolla caramelizada, pepinillos",
            price: "1050",
          },
          {
            name: "Locura Not Burger",
            description: "Medallón not burger, guacamole, tomate, cebolla caramelizada, huevo frito",
            price: "1050",
          },
          {
            name: "Remolacha Pasión",
            description: "Medallón de remolacha, tomates cherry, mozzarella",
            price: "950",
          },
        ],
      },
      tapas: {
        products: [
          {
            name: "Papas con Cheddar",
            description: "Papas fritas con salsa cheddar",
            price: "550",
          },
          {
            name: "Papas Fogosas",
            description: "Papas fritas con salsa picante",
            price: "550",
          },
          {
            name: "Nachos Completos",
            description: "Nachos con queso cheddar y dip de guacamole",
            price: "750",
          },
          {
            name: "Mozzarellas Pasión",
            description: "Triángulos de queso mozzarella rebozados (6) con salsa de toma y guacamole",
            price: "950",
          },
        ],
      },
      drinks: {
        products: [
          {
            name: "Coca Cola Lata 354ml",
            price: "250",
          },
          {
            name: "Sprite Lata 354ml",
            price: "250",
          },
          {
            name: "Agua Botella 500ml",
            price: "250",
          },
          {
            name: "Porrón Patagonia 500ml",
            price: "450",
          },
          {
            name: "Botella Patagonia 1 litro",
            price: "950",
          },
        ],
      },
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
