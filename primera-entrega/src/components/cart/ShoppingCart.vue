<template>
  <div>
    <div class="cart" type="button" data-bs-toggle="offcanvas" data-bs-target="#offcanvasExample" aria-controls="offcanvasExample">
      <span class="cart__indicator">{{ totalInCart }}</span>
      <font-awesome-icon class="cart__icon" icon="fa-solid fa-cart-shopping" />
    </div>
    <div class="offcanvas offcanvas-end" tabindex="-1" id="offcanvasExample" aria-labelledby="offcanvasExampleLabel">
      <div class="offcanvas-header">
        <h5 class="offcanvas-title" id="offcanvasExampleLabel">Mi pedido</h5>
        <button type="button" class="btn-close" data-bs-dismiss="offcanvas" aria-label="Close"></button>
      </div>
      <div class="offcanvas-body">
        <TableCart :cart="cart" />
      </div>
    </div>
  </div>
</template>

<script>
import TableCart from "@/components/cart/TableCart.vue";

export default {
  name: "ShoppingCart",
  components: {
    TableCart,
  },
  props: {
    cart: {
      type: Array,
      required: true,
    },
  },
  computed: {
    totalInCart() {
      let total = 0;
      this.cart.forEach((el) => {
        total += el.quantity;
      });
      return total;
    },
  },
};
</script>

<style lang="scss" scoped>
@import "@/assets/scss/main.scss";
.cart {
  position: fixed;
  cursor: pointer;
  top: 10vh;
  right: 10vw;
  z-index: 998;
  padding: 2rem;
  border-radius: 100%;
  margin-top: 0.5rem;
  height: 5vh;
  width: 5vw;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 0.4s ease-in-out;
  background-color: $primary;
}

.cart__indicator {
  background-color: $black;
  color: $light-gray;
  border-radius: 50%;
  z-index: 15;
  text-align: center;
  position: absolute;
  top: -15%;
  left: 55%;
  margin-top: 0.5em;
  margin-left: 0.5em;
  padding: 0.05em 0.5em;
  min-width: 1.75em;
  min-height: 1.75em;
}

.cart__icon {
  color: $light-gray;
  height: 5vh;
  width: 5vw;
  min-height: 30px;
  min-width: 30px;
}

.offcanvas {
  width: 500px;
}

.offcanvas-title {
  font-size: $size3;
}

</style>
