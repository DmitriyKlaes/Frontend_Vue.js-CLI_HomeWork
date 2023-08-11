<template>
  <div class="product">
    <h2 class="prodict__name">Название: {{ product.name }}</h2>
    <p :class="product.available ? 'avaliable' : 'missing'" class="product__price">
      Цена: {{ formattedPrice }}
    </p>
    <p v-if="product.available" class="product__available available">Есть в наличии</p>
    <p v-else class="product__available missing">Ожидаем поступления</p>
  </div>
</template>

<script>
export default {
  name: 'Product',
  data() {
    return {};
  },
  props: {
    product: Object,
  },
  methods: {},
  computed: {
    formattedPrice: function () {
      return '$' + this.product.price;
    },
  },
};
</script>

<style lang="scss" scoped>
.product {
  display: flex;
  align-items: center;
  flex-direction: column;
  justify-content: space-between;
  height: 100px;
  border: 1px solid black;

  &__price {
    font-weight: 600;
    font-size: large;
    color: green;
  }
}

.available {
  color: green;
}

.missing {
  color: red;
}
</style>
