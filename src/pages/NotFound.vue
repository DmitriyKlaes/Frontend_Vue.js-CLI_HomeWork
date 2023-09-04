<template>
  <main class="main">
    <article class="info">
      <h1 class="head">404</h1>
      <p class="text">We are sorry, but the page you requested was not found</p>
      <MainButton linkName="Back To Home" linkUrl="/" />
    </article>
    <img class="img" :src="this.img" alt="img" />
  </main>
</template>

<script>
import MainButton from '@/components/MainButton.vue';

export default {
  name: 'NotFound',
  created() {},
  data() {
    return {
      img: require('@/assets/img/img404.jpg'),
    };
  },
  props: {},
  methods: {},
  components: { MainButton },
};
</script>

<style lang="scss" scoped>
@import '@/assets/styles/_mixins.scss';
@import '@/assets/styles/_vars.scss';
@import '@/assets/styles/text-style.scss';

.main {
  max-height: 1040px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 1560px;
  padding-left: 350px;
  margin: 50px auto 100px;
  gap: 20px;
}
.info {
  max-width: 570px;
}
.head {
  @include fontStyle(250px, #cda274);
}
.text {
  color: $textColor;
  font-size: 35px;
  font-style: normal;
  font-weight: 400;
  line-height: 150%;
  letter-spacing: 0.35px;
}
.img {
  border-radius: 0 0 0 35%;
  max-width: 100%;
}
</style>
