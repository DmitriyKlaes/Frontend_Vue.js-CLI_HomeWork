<template>
  <div>
    <section class="banner" :style="backgroundImage">
      <article v-show="this.isActiveHead" class="banner__head">
        <h1 class="banner__title">{{ this.title }}</h1>
        <p class="banner__text">{{ this.text }}</p>
      </article>
    </section>
  </div>
</template>

<script>
export default {
  name: 'TopBanner',
  created() {},
  data() {
    return {};
  },
  props: {
    bannerUrl: String,
    isActiveHead: Boolean,
    title: String,
    text: String,
  },
  computed: {
    backgroundImage() {
      return {
        backgroundImage: 'url(' + this.bannerUrl + ')',
      };
    },
  },
  methods: {},
};
</script>

<style lang="scss" scoped>
@import '@/assets/styles/_mixins.scss';
@import '@/assets/styles/_vars.scss';
@import '@/assets/styles/text-style.scss';

.banner {
  background-repeat: no-repeat;
  background-position: center;
  display: flex;
  align-items: flex-end;
  height: 356px;
  max-width: 1920px;
  margin: 0 auto;
  margin-top: 50px;
  margin-bottom: 200px;

  &__head {
    max-width: 500px;
    margin: 0 auto;
    text-align: center;
    background: #fff;
    padding: 41px 78px;
    border-radius: 37px 37px 0px 0px;
  }

  &__title {
    @include fontStyle(50px, $textColor);
  }

  &__text {
    font-family: $smallTextFont;
    @extend %secondaryTextstyle;
  }
}
</style>
