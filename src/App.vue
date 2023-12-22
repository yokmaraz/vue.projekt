<!-- App.vue -->

<template>
  <div id="app">
    <Header />
    <ProductList :products="products" />
    <Footer />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';
import ProductList from './components/ProductList.vue';

export default {
  name: 'App',
  components: {
    Header,
    Footer,
    ProductList
  },
  data() {
    return {
      products: [
        { 
          id: 1, 
          name: 'Whole Lotta Red', 
          description: 'Eine Schallplatte für jedes alter geignet', 
          price: '14', 
          rating: 4,
          image: '1.png'
        },
        {
          id: 2, 
          name: 'C4', 
          description: 'Ein produkt, wenn man sich den tag verschönern will', 
          price: '50', 
          rating: 3,
          image: '2.png'
        },
        {
          id: 3, 
          name: 'Lego Ninjago 9441 Kais Feuer-Bike', 
          description: 'Für 2000er kinder', 
          price: '12', 
          rating: 4,
          image: '3.png' // Updated image name
        }
      ]
    };
  }
};
</script>

<style>

body {
  background-color: #ff0000; 
  color: #fff; 
}


</style>