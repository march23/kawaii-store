<template>
  <div class="col-sm-6">
    <ul class="list-group">
      <li class="list-group-item d-flex justify-content-between align-items-center" v-for="product in products">
          {{product.name}}
          <span class="badge badge-primary badge-pill">
            {{product.quantity}}
            <button class="btn btn-primary btn-sm" type="button" @click="updateProductQuantity(product, 'increase')" >+</button>
            <button class="btn btn-primary btn-sm" type="button" @click="updateProductQuantity(product, 'decrease')">-</button>
          </span>
      </li>
    </ul>
  </div>
</template>

<script>
  export default {
    name: 'ListProduct',
    props: {
      products: Array
    },
    methods: {
      updateProductQuantity: function(product, type){
        type == 'increase' ?  product.quantity++ : product.quantity--
      }
    }
  }
</script>