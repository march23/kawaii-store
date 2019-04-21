<template>
  <form class="form" action="/action_page.php">
    <div class="form-group">
      <label>Name:</label>
      <input type="text" class="form-control" v-model="product.name"/>
    </div>
    <div class="form-group">
      <label>Description:</label>
      <input type="text" class="form-control" v-model="product.description"/>
    </div>
    <div class="form-group">
      <label>Quantity:</label>
      <input type="number" class="form-control" v-model="product.quantity"/>
    </div>
    <button type="button" class="btn btn-success" @click="createProduct">Add Product</button>
  </form>
</template>

<script>
  export default {
    name: 'CreateProduct',
    data: function(){
      return {
        product: {
          name: '',
          description: '',
          quantity: 0
        }
      }
    },
    methods: {
      createProduct: function () {
        this.$emit('create-product', {...this.product})
      }
    }
  }
</script>