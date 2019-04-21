<template>
  <div>
    <div class="card-deck">
      <create-product v-on:create-product="addProduct"></create-product>
      <list-product :products="products"></list-product>  
    </div>
    <br/>
    <span>Total: {{totalProducts}}</span>
  </div>
</template>

<script>
import CreateProduct from './CreateProduct.vue'
import ListProduct from './ListProduct.vue'

export default {
  name: 'Dashboard',
  components: {
    CreateProduct,
    ListProduct
  },
  data: function(){
    return { 
      products: [],
    }
  },
  computed: {
    totalProducts: function () {
      return this.products.length
    }
  },
  methods: {
    addProduct: function(newProduct){
      this.products.push(newProduct)
    }
  }
}
</script>

<style>
  body {
    background-image: url('../assets/kawaii.jpg');
    background-repeat: no-repeat;
    background-position: center;
  }
</style>
