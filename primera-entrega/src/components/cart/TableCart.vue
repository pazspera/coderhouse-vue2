<template>
  <table class="table">
    <thead>
      <tr>
        <th scope="col" v-for="(title, t) in tableTitles" :key="t">{{ title }}</th>
      </tr>
    </thead>
    <tbody>
      <tr scope="row" v-for="(product, p) in cart" :key="p">
        <td>{{ product.name }}</td>
        <td>{{ product.quantity }}</td>
        <td>{{ product.price }}</td>
        <td>{{ product.total }}</td>
      </tr>
      <tr>
        <td colspan="4">Total: {{ calculateTotal }}</td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  name: "TableCart",
  props: {
    cart: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
      tableTitles: ["Producto", "Cantidad", "Precio", "Total"],
    };
  },
  computed: {
    calculateTotal() {
      let totalInCart = Number(0);
      this.cart.forEach((product) => {
        totalInCart += Number(product.total);
      });
      return Number(totalInCart);
    },
  },
};
</script>

<style></style>
