<template>
  <div>
    <h1>Guitar Products</h1>
    <div v-for="product in products" :key="product.id">
      <guitar-product :product="product"></guitar-product>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import ProductsComp from '../src/components/ProductsComp.vue';

export default {
  components: {
    ProductsComp
  },
  data() {
    return {
      products: []
    };
  },
  mounted() {
    axios
      .get('https://jcgviljoen.github.io/json-guitar-server/products.json') 
      .then(response => {
        this.products = response.data.products;
      })
      .catch(error => {
        console.error('Error fetching data:', error);
      });
  }
};
</script>
