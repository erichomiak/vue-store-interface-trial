<template>
  <div id="app">
    <Header />
    <AddProduct v-on:add-product="AddProduct" />
    <Products v-bind:products="products" v-on:del-product="deleteProduct" />
  </div>
</template>

<script>
import Header from './components/layout/Header';
import Products from './components/Products';
import AddProduct from './components/AddProduct';

export default {
  name: 'App',
  components: {
    Header,
    Products,
    AddProduct
  }, 
  data() {
    return {
      products: [
        {
          id: 'NBZNH4C1CW',
          title: 'Oranges',
          price: '2.99',
          description: 'Fresh picked this morning'
        },
        {
          id: 'PSCET9WM16',
          title: 'Tomatoes',
          price: '1.99',
          description: 'Ripe and juicy'
        },
        {
          id: 'OF4318Z635',
          title: 'Apples',
          price: '2.49',
          description: 'Crisp and fresh'
        },
      ]
    }
  },
  methods: {
    deleteProduct(id) {
      this.products = this.products.filter(product => product.id !== id);
    },
    AddProduct(newProduct) {
      this.products = [...this.products, newProduct];
    }
  }
}
</script>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }

  .btn {
    display: inline-block;
    border: none;
    background: #444;
    color: #fff;
    padding: 7px 20px;
    cursor: pointer;
  }

  .btn:hover {
    background: #555;
  }
</style>
