<template>
  <div class="project-box">
    <section class="content__tag-box">
      <div class="content__tag" v-for="tag in this.tags" :key="tag.id">
        <input
          class="content__item checkbox-none"
          type="radio"
          :id="tag.id"
          name="tag"
          @change="activeTag(tag.id)" />
        <label class="content__checkbox" :for="tag.id">{{ tag.text }}</label>
      </div>
    </section>
    <input
      @change="this.isFavorite = !this.isFavorite"
      class="content__item checkbox-none"
      id="only"
      type="checkbox" />
    <label class="content__checkbox favorite" for="only">Favorites ONLY</label>
    <section class="articles-box">
      <article
        :class="item.tag"
        v-for="item in favorites"
        :key="item.id"
        class="articles-box__item">
        {{ item.tag }}
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
  </div>
</template>

<script>
export default {
  name: "Project",
  data() {
    return {
      tags: [
        {
          id: "kitchen",
          text: "Kitchen",
        },
        {
          id: "bathroom",
          text: "Bathroom",
        },
        {
          id: "bedroom",
          text: "Bedroom",
        },
        {
          id: "livingroom",
          text: "Living room",
        },
      ],
      data: [
        {
          id: "post11",
          dataid: "kitchen",
          favorite: false,
          tag: "kitchen",
          text: "lorem123",
        },
        {
          id: "post11",
          dataid: "bathroom",
          favorite: false,
          tag: "bathroom",
        },
        {
          id: "post11",
          dataid: "bedroom",
          favorite: false,
          tag: "bedroom",
        },
        {
          id: "post11",
          dataid: "livingroom",
          favorite: false,
          tag: "livingroom",
        },
        {
          id: "post11",
          dataid: "kitchen",
          favorite: false,
          tag: "kitchen",
        },
        {
          id: "post11",
          dataid: "bathroom",
          favorite: false,
          tag: "bathroom",
        },
        {
          id: "post11",
          dataid: "bedroom",
          favorite: false,
          tag: "bedroom",
        },
        {
          id: "post11",
          dataid: "livingroom",
          favorite: false,
          tag: "livingroom",
        },
        {
          id: "post11",
          dataid: "kitchen",
          favorite: false,
          tag: "kitchen",
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
.project-box {
  width: 800px;
  margin: 0 auto;
}
.content__tag-box {
  margin-top: 40px;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 10px;
}
.content__tag {
  margin-bottom: 25px;
}
.content__item {
  margin-top: 10px;
  &:checked + label {
    background-color: #292f36;
    color: #fff;
  }
}
.checkbox-none {
  position: absolute;
  left: -9999999px;
  display: none;
}
.content__checkbox {
  border-radius: 10px;
  background: #f4f0ec;
  padding: 10px 30px;
  text-align: center;
  letter-spacing: 0.36px;
}
.articles-box {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  &__item {
    width: 390px;
    height: 100px;
    font-size: 30px;
    border: 1px solid black;
    display: flex;
    justify-content: space-between;
  }
  &__favorite {
    width: 30px;
    height: 30px;
  }
}
.favorite {
  display: block;
  padding-bottom: 15px;
  padding-top: 10px;
  width: 300px;
  margin: 0 auto;
}
.kitchen {
  background-color: #955f5f;
}
.bathroom {
  background-color: #689166;
}
.bedroom {
  background-color: #d0e25a;
}
.livingroom {
  background-color: #537c99;
}
</style>
