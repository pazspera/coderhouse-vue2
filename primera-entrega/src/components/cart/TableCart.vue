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
        <td class="text-center">{{ product.quantity }}</td>
        <td class="text-center">{{ product.price }}</td>
        <td class="text-center">{{ product.total }}</td>
      </tr>
    </tbody>
    <tfoot>
      <tr>
        <td colspan="4">Total del pedido: {{ calculateTotal }}</td>
      </tr>
    </tfoot>
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
    // calculateTotal() estaba tomando los valores como strings así que los
    // convierto a todos a number para poder hacer la operación
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

<style lang="scss" scoped>
@import "@/assets/scss/main.scss";

th {
  font-weight: 600;
}
</style>
