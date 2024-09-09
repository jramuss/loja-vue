<template>
  <div>
    <h1>Carrinho de Compras</h1>
    <div v-for="item in cartItems" :key="item.id">
      <p>{{ item.name }} - R$ {{ item.price.toFixed(2) }}</p>
    </div>
    <p>Total: R$ {{ totalPrice.toFixed(2) }}</p>
  </div>
</template>
  
<script>
  export default {
    props: ['cartItems'],
    computed: {
      totalPrice() {
        return this.cartItems.reduce((total, item) => total + item.price, 0)
      }
    }
  }
</script>
  