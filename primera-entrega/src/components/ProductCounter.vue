<template>
  <div class="my-3">
    <button @click="decreaseCounter()">-</button>
    {{ counter }}
    <button @click="increaseCounter()">+</button>
  </div>
</template>

<script>
export default {
  name: "ProductCounter",
  data() {
    return {
      counter: 1,
    };
  },
  methods: {
    increaseCounter() {
      this.counter++;
    },
    decreaseCounter() {
      if (this.counter > 1) {
        this.counter--;
      }
    },
  },
};
</script>

<style></style>
