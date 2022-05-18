<template>
  <div class="my-3">
    <button @click="decreaseCounter()">-</button>
    <span>{{ counter }}</span>
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
      ProductCard lo recibe y al addToCart hacemos que pase un objeto 
      con this.product.id y counter que recibió
    */
    increaseCounter() {
      this.counter++;
      this.$emit("update-counter", this.counter);
    },
    decreaseCounter() {
      if (this.counter > 0) {
        this.counter--;
        this.$emit("update-counter", this.counter);
      }
    },
  },
};
</script>

<style lang="scss" scoped>
@import "@/assets/scss/main.scss";

span {
  margin: 0 $size6;
}

button {
  border-top-color: $black;
  background-color: $black;
  color: $light-gray;
  border-bottom-color: $black;
  border-left-color: $black;
  border-right-color: $black;
  height: $size3;
  width: $size3;
}
</style>
