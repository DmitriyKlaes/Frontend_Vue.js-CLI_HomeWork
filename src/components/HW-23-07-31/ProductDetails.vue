<template>
  <div class="product-box">
    <Product :product="product" v-for="product in this.products" :key="product.id" />
    <section class="prodict"></section>
  </div>
</template>

<script>
import Product from './Product.vue';

export default {
  name: 'ProductDetails',
  components: {
    Product,
  },
  data() {
    return {
      products: [
        { name: 'Батон', price: 9.5, available: true },
        { name: 'Яблоки', price: 20, available: false },
        { name: 'Греча', price: 15.1, available: false },
        { name: 'Кура', price: 35.4, available: true },
        { name: 'Молоко', price: 13.7, available: false },
        { name: 'Пивасик', price: 100, available: true },
      ],
    };
  },
  props: {},
  methods: {},
};
</script>

<style lang="scss" scoped>
.product-box {
  max-width: 1200px;
  display: grid;
  grid-template-columns: repeat(2, minmax(auto, 100%));
  gap: 20px;
  margin: 50px auto;
}
</style>
