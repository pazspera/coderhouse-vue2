<template>
  <main id="app">
    <NavBar />
    <ShoppingCart :cart="cart" />

    <section class="container my-5">
      <div class="row">
        <div class="col">
          <h2 class="mb-3">Hamburguesas</h2>
        </div>
      </div>
      <div class="row row-cols-1 row-cols-md-2 row-cols-lg-3 g-4">
        <ProductCard v-for="product in hamburgers" :key="product.id" :product="product" @add-to-cart="updateCart" />
      </div>
    </section>

    <section class="container my-5">
      <div class="row">
        <div class="col">
          <h2 class="mb-3">Tapas</h2>
        </div>
      </div>
      <div class="row row-cols-1 row-cols-md-2 row-cols-lg-3 g-4">
        <ProductCard v-for="product in tapas" :key="product.id" :product="product" @add-to-cart="updateCart" />
      </div>
    </section>

    <section class="container my-5">
      <div class="row">
        <div class="col">
          <h2 class="mb-3">Bebidas</h2>
        </div>
      </div>
      <div class="row row-cols-1 row-cols-md-2 row-cols-lg-3 g-4">
        <ProductCard v-for="product in drinks" :key="product.id" :product="product" @add-to-cart="updateCart" />
      </div>
    </section>
  </main>
</template>

<script>
import ProductCard from "@/components/ProductCard.vue";
import ShoppingCart from "@/components/ShoppingCart.vue";
import NavBar from "@/components/NavBar.vue";

export default {
  name: "App",
  components: {
    ProductCard,
    ShoppingCart,
    NavBar,
  },
  mounted() {
    // A la carga del documento se dividen los datos de products en categorías,
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
      cart: [],
    };
  },
  methods: {
    filterProducts(array, category) {
      // Recibe todos los productos y, en base a la categoría de producto, se guarda
      // en un array por categoría (hamburgers, tapas, drinks)
      let filteredArray = array.filter((product) => product.category === category);
      return filteredArray;
    },
    updateCart(productId, productCounter) {
      // Revisa si el addedProduct ya existe en el cart
      let addedProduct = this.cart.find((product) => product.id === productId);

      // Si addedProduct no está en el array devuelve undefined que es falsy
      if (addedProduct) {
        // Actualiza cantidad y total si producto está en cart
        addedProduct.quantity = productCounter;
        addedProduct.total = addedProduct.quantity * addedProduct.price;
        console.log(addedProduct);
      } else {
        // Recuperar datos de producto de products[]
        let newProduct = this.products.find((product) => product.id === productId);
        // Agrega cantidad y total a nuevos productos
        newProduct.quantity = productCounter;
        newProduct.total = newProduct.price;
        this.cart.push(newProduct);
      }
    }
  },
};
</script>

<style>
#app {
  margin: 0;
}
</style>
