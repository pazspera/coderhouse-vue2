<template>
  <div class="col">
    <table class="table">
      <thead>
        <tr>
          <th scope="col" v-for="(title, t) in titles" :key="t">{{ title }}</th>
        </tr>
      </thead>
      <tbody>
          <tr v-for="(product, p) in products" :key="p">
              <td>{{ p + 1 }}</td>
              <td v-for="(row, r) in product" :key="r">{{ row }}</td>
          </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: "TableProducts",
  props: {
    titles: {
      type: Array,
      required: true,
    },
    products: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style></style>
