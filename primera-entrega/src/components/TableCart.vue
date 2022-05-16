<template>
  <table class="table">
    <thead>
      <tr>
        <th scope="col" v-for="(title, t) in tableTitles" :key="t">{{ title }}</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td></td>
      </tr>
    </tbody>
    <p>{{ cart }}</p>
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
    products: {
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
