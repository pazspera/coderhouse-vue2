<template>
  <table class="table">
    <thead>
      <tr>
        <th scope="col" v-for="(title, t) in tableTitles" :key="t">{{ title }}</th>
      </tr>
    </thead>
  </table>
</template>

<script>
export default {
  name: "TableCart",
  data() {
    return {
      tableTitles: ["Producto", "Cantidad", "Precio", "Total"],
    };
  },
};
</script>

<style></style>
