<template>
  <div>
    <button class="cart" type="button" data-bs-toggle="offcanvas" data-bs-target="#offcanvasExample" aria-controls="offcanvasExample"><font-awesome-icon icon="fa-solid fa-cart-shopping" /></button>
    <div class="offcanvas offcanvas-end" tabindex="-1" id="offcanvasExample" aria-labelledby="offcanvasExampleLabel">
      <div class="offcanvas-header">
        <h5 class="offcanvas-title" id="offcanvasExampleLabel">Mi pedido</h5>
        <button type="button" class="btn-close" data-bs-dismiss="offcanvas" aria-label="Close"></button>
      </div>
      <div class="offcanvas-body">
        <div>Some text as placeholder. In real life you can have the elements you have chosen. Like, text, images, lists, etc.</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ShoppingCart",
};
</script>

<style>
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
}

.fa-solid {
  color: black;
}

.fa-cart-shopping {
  height: 5vh;
  width: 5vw;
  min-height: 30px;
  min-width: 30px;
}
</style>
