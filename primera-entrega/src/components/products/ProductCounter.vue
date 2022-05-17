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
    /*  
      increaseCounter() y decreaseCounter() mandan al ProductCard la cantidad
      actualizada cada vez que se hace click en el ProductCounter
      ProductCard lo recibe y al addToCart hacemos que pase un objeto con this.product.id y counter que recibió
    */
    increaseCounter() {
      this.counter++;
      this.$emit("update-counter", this.counter);
      console.log(this.counter);
    },
    decreaseCounter() {
      if (this.counter > 0) {
        this.counter--;
        this.$emit("update-counter", this.counter);
        console.log(this.counter);
      }
    },
  },
};
</script>

<style></style>
