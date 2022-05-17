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
};
</script>

<style></style>
