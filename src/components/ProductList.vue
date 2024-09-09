<template>
    <div>
      <h1>Lista de Produtos</h1>
      <div v-for="product in products" :key="product.id" class="product-item">
        <img :src="product.image" alt="Product Image" />
        <h2>{{ product.name }}</h2>
        <p>Preço: R$ {{ product.price.toFixed(2) }}</p>
        <button @click="addToCart(product)">Adicionar ao Carrinho</button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: ['products'],
    methods: {
      addToCart(product) {
        this.$emit('add-to-cart', product)
      }
    }
  }
  </script>
  
  <style scoped>
  .product-item {
    border: 1px solid #ccc;
    padding: 10px;
    margin: 10px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  </style>
  