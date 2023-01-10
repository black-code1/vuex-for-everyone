<template>
  <div>
    <h1>Shopping Cart</h1>
    <ul>
      <li v-for="product in products">
        {{product.title}} - {{product.price | currency}} - {{product.quantity}}
      </li>
    </ul>
    <p>Total: {{total | currency}}</p>
    <button @click="checkout">Checkout</button>
    <p v-if="checkoutStatus">{{checkoutStatus}}</p>
  </div>
</template>

<script>
import store from "../store";

export default {
  name: "ShoppingCart",
  methods: {
    checkout () {
      return store.dispatch('checkout')
    }
  },
  computed: {
    products () {
      return store.getters.cartProducts
    },
    total () {
      return store.getters.cartTotal
    },
    checkoutStatus () {
      return store.state.checkoutStatus
    }
  }
}
</script>

<style scoped>

</style>
