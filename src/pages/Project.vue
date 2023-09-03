<template>
  <main>
    <section class="banner">
      <article class="banner__head">
        <h1 class="banner__title">Our Project</h1>
        <p class="banner__text">Home / Project</p>
      </article>
    </section>
    <div class="project-box">
      <section class="project__tag-box">
        <div class="project__tag" v-for="tag in this.tags" :key="tag.id">
          <input
            class="project__item checkbox-none"
            type="radio"
            :id="tag.id"
            name="tag"
            @change="activeTag(tag.id)" />
          <label class="project__checkbox" :for="tag.id">{{ tag.text }}</label>
        </div>
      </section>
      <input
        @change="this.isFavorite = !this.isFavorite"
        class="project__item checkbox-none"
        id="only"
        type="checkbox" />
      <label class="project__checkbox favorite" for="only"
        >Favorites ONLY</label
      >
      <section class="articles-box">
        <article
          v-for="item in favorites"
          :key="item.id"
          class="articles-box__item">
          <img :src="item.src" alt="img" class="articles-box__img" />
          <section class="articles-box__info">
            <div class="articles-box__text-container">
              <h3 class="articles-box__heading">{{ item.info }}</h3>
              <p class="articles-box__text-item">Decor / Artchitecture</p>
            </div>
            <a href="#" class="articles-box__link">
              <div class="articles-box__button">
                <svg
                  width="70"
                  height="70"
                  viewBox="0 0 70 70"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg">
                  <circle cx="35" cy="35" r="35" fill="#F4F0EC" />
                  <path
                    d="M32 44L40 35L32 26"
                    stroke="#292F36"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round" />
                </svg>
              </div>
            </a>
          </section>
          <img
            @click="item.favorite = !item.favorite"
            :src="
              item.favorite
                ? require('@/assets/img/favorite2.png')
                : require('@/assets/img/favorite1.png')
            "
            alt="favorite"
            class="articles-box__favorite" />
        </article>
      </section>
      <div class="project__pagination">
        <img src="@/assets/img/pagination.png" alt="pagination" />
      </div>
    </div>
  </main>
</template>

<script>
export default {
  name: 'Project',
  data() {
    return {
      tags: [
        {
          id: 'kitchen',
          text: 'Kitchen',
        },
        {
          id: 'bathroom',
          text: 'Bathroom',
        },
        {
          id: 'bedroom',
          text: 'Bedroom',
        },
        {
          id: 'livingroom',
          text: 'Living room',
        },
      ],
      data: [
        {
          dataid: 'kitchen',
          favorite: false,
          info: 'kitchen-1',
          src: require('@/assets/img/кухня1.jpg'),
        },
        {
          dataid: 'bathroom',
          favorite: false,
          info: 'bathroom-1',
          src: require('@/assets/img/ванная1.jpg'),
        },
        {
          dataid: 'bedroom',
          favorite: false,
          info: 'bedroom-1',
          src: require('@/assets/img/спальня1.jpg'),
        },
        {
          dataid: 'livingroom',
          favorite: false,
          info: 'livingroom-1',
          src: require('@/assets/img/комната1.jpg'),
        },
        {
          dataid: 'kitchen',
          favorite: false,
          info: 'kitchen-2',
          src: require('@/assets/img/кухня2.jpg'),
        },
        {
          dataid: 'bathroom',
          favorite: false,
          info: 'bathroom-2',
          src: require('@/assets/img/ванная2.jpg'),
        },
        {
          dataid: 'bedroom',
          favorite: false,
          info: 'bedroom-2',
          src: require('@/assets/img/спальня2.jpg'),
        },
        {
          dataid: 'livingroom',
          favorite: false,
          info: 'livingroom-2',
          src: require('@/assets/img/комната2.jpg'),
        },
        {
          dataid: 'kitchen',
          favorite: false,
          info: 'kitchen-3',
          src: require('@/assets/img/кухня3.jpg'),
        },
      ],
      isFavorite: false,
    };
  },
  props: {},
  methods: {
    activeTag(tag) {
      this.data.sort((a, b) => {
        if (a.dataid !== tag && b.dataid === tag) return 1;
        if (a.dataid === tag && b.dataid === tag) return 0;
        return -1;
      });
    },
  },
  computed: {
    favorites() {
      if (this.isFavorite) return this.data.filter((value) => value.favorite);
      else return this.data;
    },
  },
};
</script>

<style lang="scss" scoped>
@import '@/assets/styles/_mixins.scss';
@import '@/assets/styles/_vars.scss';

%secondaryTextstyle {
  color: $secondTextColor;
  font-size: 22px;
  font-style: normal;
  font-weight: 400;
  line-height: 150%;
}

.banner {
  background-image: url('@/assets/img/project-banner.jpg');
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

.project-box {
  max-width: $siteWidth;
  margin: 0 auto 200px;
}
.project__tag-box {
  max-width: 880px;
  min-height: 75px;
  margin: 0 auto;
  display: flex;
  flex-wrap: wrap;
  border: 1px solid #cda274;
  border-radius: 18px;
}
.project__tag {
  width: 220px;
}
.content__tag {
}
.project__item {
  margin-top: 10px;
  &:checked + label {
    background-color: #cda274;
    color: #fff;
  }
}
.checkbox-none {
  position: absolute;
  left: -9999999px;
  display: none;
}
.project__checkbox {
  width: 100%;
  border-radius: 18px;
  padding: 26px 30px;
  display: inline-block;
  box-sizing: border-box;
  color: $textColor;
  text-align: center;
  font-family: $smallTextFont;
  font-size: 18px;
  font-style: normal;
  font-weight: 600;
  line-height: 125%;
  letter-spacing: 0.36px;
}
.articles-box {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  &__item {
    width: 590px;
    font-size: 30px;
    display: flex;
    justify-content: space-between;
    flex-direction: column;
    box-sizing: border-box;
    position: relative;
    gap: 15px;
  }
  &__info {
    display: flex;
    justify-content: space-between;
  }
  &__img {
    width: 100%;
  }
  &__text-container {
    display: flex;
    flex-direction: column;
  }
  &__heading {
    @include fontStyle(25px, $textColor);
    letter-spacing: 0.5px;
  }
  &__text-item {
    font-family: $smallTextFont;
    @extend %secondaryTextstyle;
    letter-spacing: 0.22px;
  }
  &__favorite {
    width: 30px;
    height: 30px;
    position: absolute;
    right: 0;
  }
}
.favorite {
  height: 75px;
  display: block;
  width: 220px;
  margin: 5px auto 0;
  margin-bottom: 60px;
  border: 1px solid #cda274;
  border-radius: 18px;
}
.project__pagination {
  margin: 60px auto 200px;
  display: flex;
  justify-content: center;
}
</style>
