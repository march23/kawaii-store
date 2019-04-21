<template>
    <ul class="list-group">
      <li class="list-group-item d-flex justify-content-between align-items-center" v-for="product in products">
          {{product.name}}
          <span class="badge badge-primary badge-pill">{{product.quantity}}</span>
      </li>
    </ul>
</template>

<script>
  export default {
    name: 'ListProduct',
    props: {
      products: Array
    }
  }
</script>