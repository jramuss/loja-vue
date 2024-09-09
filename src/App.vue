<template>
  <div id="app">
    <ProductList :products="products" @add-to-cart="addToCart" />
    <Cart :cartItems="cart" />
  </div>
</template>

<script>
import ProductList from './components/ProductList.vue'
import Cart from './components/ShopCart.vue'

export default {
  components: {
    ProductList,
    Cart
  },
  data() {
    return {
      products: [
        { id: 1, name: 'Camiseta', price: 49.99, image: 'https://via.placeholder.com/150' },
        { id: 2, name: 'Tênis', price: 149.99, image: 'https://via.placeholder.com/150' },
        { id: 3, name: 'Boné', price: 29.99, image: 'https://via.placeholder.com/150' }
      ],
      cart: []
    }
  },
  methods: {
    addToCart(product) {
      this.cart.push(product)
    }
  }
}
</script>
