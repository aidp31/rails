<template>
    <div>
      <h1>Productos</h1>
      <ul>
        <li v-for="product in products" :key="product.id">
          {{ product.name }} - {{ product.price }}
        </li>
      </ul>
    </div>
  </template>
  
  <script >
  export default {
    data() {
      return {
        products: [],
      };
    },
    created() {
      fetch("https://dummyjson.com/products")
        .then((response) => response.json())
        .then((data) => {
          this.products = data;
        });
    },
  };
  </script>
  
  <style scoped>
  h1 {
    color: #2c3e50;
  }
  </style>