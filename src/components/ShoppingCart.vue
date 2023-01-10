<template>
  <div>
    <h1>Shopping Cart</h1>
    <ul>
      <li v-for="product in products">
        {{product.title}} - {{product.price | currency}} - {{product.quantity}}
      </li>
    </ul>
    <p>Total: {{total | currency}}</p>
  </div>
</template>

<script>
import store from "../store";

export default {
  name: "ShoppingCart",
  computed: {
    products () {
      return store.getters.cartProducts
    },
    total () {
      return store.getters.cartTotal
    }
  }
}
</script>

<style scoped>

</style>
