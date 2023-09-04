<template>
  <main>
    <section class="blog-promo">
      <article class="blog-promo__head">
        <h1 class="blog-promo__title">Articles & News</h1>
        <p class="blog-promo__text">Home / Blog</p>
      </article>
    </section>
    <section class="content">
      <h2 class="content__title">Latest Post</h2>
      <section class="latest-post">
        <img
          class="latest-post__img"
          src="@/assets/img/last-post.png"
          alt="post" />
        <div class="latest-post__content">
          <h2 class="latest-post__heading">
            Low Cost Latest Invented Interior Designing Ideas
          </h2>
          <div class="latest-post__text-box">
            <p class="latest-post__text">
              Lorem ipsum dolor sit amet, adipiscing Aliquam eu sem vitae turpis
              dignissim maximus.posuere in.Contrary to popular belief.
            </p>
            <p class="latest-post__text">
              Lorem Ipsum is not simply random text. It has roots in a piece of
              classica.
            </p>
          </div>
          <div class="latest-post__datelink">
            <p class="latest-post__date">30 July, 2023</p>
            <router-link to="/blogdetails" class="latest-post__link">
              <svg
                width="52"
                height="53"
                viewBox="0 0 52 53"
                fill="none"
                xmlns="http://www.w3.org/2000/svg">
                <circle cx="26" cy="26.5" r="26" fill="#F4F0EC" />
                <path
                  d="M23.771 33.1855L29.7139 26.4998L23.771 19.8141"
                  stroke="#292F36"
                  stroke-width="2"
                  stroke-linecap="round"
                  stroke-linejoin="round" />
              </svg>
            </router-link>
          </div>
        </div>
      </section>
      <h2 class="content__title">Articles & News</h2>
      <section class="bottom" id="app">
        <div class="bottom__content-blog">
          <article
            class="bottom__item"
            v-for="item in firstArrayElements(6)"
            :key="item.src">
            <div class="bottom__img-box">
              <img class="bottom__img" :src="item.src" alt="bottom-image" />
              <div class="bottom__inside">
                <p class="bottom__inside-text">{{ item.insideText }}</p>
              </div>
            </div>
            <h3 class="bottom__heading">{{ item.heading }}</h3>
            <div class="bottom__link-container">
              <p class="bottom__date">{{ item.date }}</p>
              <router-link to="/blogdetails" class="bottom__link">
                <div class="bottom__button">
                  <svg
                    width="52"
                    height="53"
                    viewBox="0 0 52 53"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg">
                    <circle cx="26" cy="26.267" r="26" fill="#F4F0EC" />
                    <path
                      d="M23.7714 32.9527L29.7143 26.267L23.7714 19.5813"
                      stroke="#292F36"
                      stroke-width="2"
                      stroke-linecap="round"
                      stroke-linejoin="round" />
                  </svg>
                </div>
              </router-link>
            </div>
          </article>
        </div>
        <div class="bottom__pagination">
          <img src="@/assets/img/pagination.png" alt="pagination" />
        </div>
      </section>
    </section>
  </main>
</template>

<script>
export default {
  name: 'Blog',
  data() {
    return {
      items: [
        {
          src: require('@/assets/img/bottom-image1.png'),
          insideText: 'Kitchan Design',
          heading: 'Let’s Get Solution For Building Construction Work',
          date: '30 july, 2023',
        },
        {
          src: require('@/assets/img/bottom-image2.png'),
          insideText: 'Living Design',
          heading: 'Low Cost Latest Invented Interior Designing Ideas.',
          date: '30 july, 2023',
        },
        {
          src: require('@/assets/img/bottom-image3.png'),
          insideText: 'Interior Design',
          heading: 'Best For Any Office & Business Interior Solution',
          date: '30 july, 2023',
        },
        {
          src: require('@/assets/img/bottom-image4.png'),
          insideText: 'Kitchan Design',
          heading: 'Let’s Get Solution For Building Construction Work',
          date: '30 july, 2023',
        },
        {
          src: require('@/assets/img/bottom-image5.png'),
          insideText: 'Living Design',
          heading: 'Low Cost Latest Invented Interior Designing Ideas.',
          date: '30 july, 2023',
        },
        {
          src: require('@/assets/img/bottom-image6.png'),
          insideText: 'Interior Design',
          heading: 'Best For Any Office & Business Interior Solution',
          date: '30 july, 2023',
        },
      ],
    };
  },
  methods: {
    firstArrayElements(number) {
      return this.items.slice(0, number);
    },
  },
};
</script>

<style lang="scss"></style>
