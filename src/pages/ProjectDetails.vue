<template>
  <TopBanner :bannerUrl="projectDetailsBannerUrl" :isActiveHead="false" />
  <section class="content">
    <h1 class="head">Minimal Look Bedrooms</h1>
    <p class="text">{{ projectDetailsInfoTop }}</p>
    <br />
    <p class="text">{{ projectDetailsInfoBottom }}</p>
  </section>
  <swiper
    :style="{
      '--swiper-navigation-color': '#000',
      '--swiper-pagination-color': '#000',
    }"
    :zoom="true"
    :navigation="true"
    :pagination="{
      clickable: true,
    }"
    :modules="modules"
    class="mySwiper">
    <swiper-slide v-for="img in prodjectDetailsSwiperImgs" :key="img.id">
      <div class="swiper-zoom-container">
        <img class="swiper-img" :src="img" />
      </div>
    </swiper-slide>
  </swiper>
</template>

<script>
import TopBanner from '@/components/TopBanner.vue';
import { mapState } from 'vuex';
import { Swiper, SwiperSlide } from 'swiper/vue';
import { Zoom, Navigation, Pagination } from 'swiper/modules';
import 'swiper/css';
import 'swiper/css/zoom';
import 'swiper/css/navigation';
import 'swiper/css/pagination';

export default {
  name: 'ProjectDetails',
  created() {},
  setup() {
    return {
      modules: [Zoom, Navigation, Pagination],
    };
  },
  components: {
    TopBanner,
    Swiper,
    SwiperSlide,
  },
  data() {
    return {};
  },
  props: {},
  methods: {},
  computed: {
    ...mapState([
      'projectDetailsBannerUrl',
      'projectDetailsInfoTop',
      'projectDetailsInfoBottom',
      'prodjectDetailsSwiperImgs',
    ]),
  },
};
</script>

<style lang="scss" scoped>
@import '@/assets/styles/_mixins.scss';
@import '@/assets/styles/_vars.scss';
@import '@/assets/styles/text-style.scss';

.swiper {
  width: 100%;
  height: 870px;
  max-width: $siteWidth;
  margin-bottom: 100px;
  border-radius: 70px;
}

.swiper-slide {
  overflow: hidden;
}

.swiper-img {
  border-radius: 70px;
}

.content {
  max-width: 660px;
  margin: 0 auto;
}
.head {
  @include fontStyle(50px, $textColor);
  letter-spacing: 1px;
  margin-bottom: 10px;
}
.text {
  font-family: $smallTextFont;
  @extend %secondaryTextstyle;
  letter-spacing: 0.22px;
}
</style>
