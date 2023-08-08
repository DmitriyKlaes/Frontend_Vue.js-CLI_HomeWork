<template>
    <main>
        <article class="blogdetails-promo"></article>
        <section class="content flex-row">
            <section class="content__post" v-show="item.isActive" v-for="item in this.articlesData" :key="item.id">
                <h2 class="content__title">Let’s Get Solution for Building Construction Work</h2>
                <img class="content__img" :src=item.srcTop alt=item.tag>
                <div class="content__history">
                    <p class="content__date">03 August, 2023</p>
                    <p class="content__breadcrumbs">Interior / Home / Decore</p>
                </div>
                <div class="content__info">
                    <p class="content__text">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Numquam possimus consequuntur repudiandae sequi corporis minus.</p>
                    <p class="content__text">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quam nostrum, ea cupiditate animi architecto reiciendis.</p>
                </div>
                <section class="content__citation">
                    <h3 class="content__heading-citation">“</h3>
                    <p class="content__text-citation">The details are not the details. They make the design.</p>
                </section>
                <h2 class="content__title">Design sprints are great</h2>
                <ol class="content__list">Lorem ipsum dolor sit amet.
                    <li class="content__list-item">Lorem ipsum dolor sit amet.</li>
                    <li class="content__list-item">Lorem ipsum dolor sit amet.</li>
                    <li class="content__list-item">Lorem ipsum dolor sit amet.</li>
                </ol>
                <img class="content__img" :src=item.srcBottom alt=item.tag>
                <p class="content__text">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Porro natus corrupti animi optio ipsum fugit vero. Minus temporibus iure hic.</p>
            </section>
            <section class="content__tags">
                <h3 class="content__heading">Tags</h3>
                <section class="content__tag-box">
                    <div class="content__tag" v-for="item in this.articlesData" :key="item.id">
                        <input v-if=item.isActive checked class="content__item checkbox-none" type="radio" :id=item.id name="tag" @change="activeTag(item)">
                        <input v-else class="content__item checkbox-none" type="radio" :id=item.id name="tag" @change="activeTag(item)">
                        <label class="content__checkbox" :for=item.id>{{ item.tag }}</label>
                    </div>
                </section>
            </section>
        </section>
    </main>
</template>

<script>

export default {
    name: 'BlogDetails',
    data() {
        return {
            articlesData: [
                {
                    id: 'post1',
                    isActive: true,
                    srcTop: require('@/assets/img/kitchen-top.jpg'),
                    srcBottom: require('@/assets/img/kitchen-bottom.png'),
                    tag: 'Kitchen',
                },
                {
                    id: 'post2',
                    isActive: false,
                    srcTop: require('@/assets/img/bedroom-top.png'),
                    srcBottom: require('@/assets/img/bedroom-bottom.jpg'),
                    tag: 'Bedroom',
                },
                {
                    id: 'post3',
                    isActive: false,
                    srcTop: require('@/assets/img/building-top.jpg'),
                    srcBottom: require('@/assets/img/building-bottom.jpg'),
                    tag: 'Building',
                },
                {
                    id: 'post4',
                    isActive: false,
                    srcTop: require('@/assets/img/architecture-top.jpg'),
                    srcBottom: require('@/assets/img/architecture-bottom.jpg'),
                    tag: 'Architecture',
                },
                {
                    id: 'post5',
                    isActive: false,
                    srcTop: require('@/assets/img/kitchen-planning-top.jpg'),
                    srcBottom: require('@/assets/img/kitchen-planning-bottom.jpg'),
                    tag: 'Kitchen Planning',
                },
                {
                    id: 'post6',
                    isActive: false,
                    srcTop: require('@/assets/img/bathroom-top.jpg'),
                    srcBottom: require('@/assets/img/bathroom-bottom.png'),
                    tag: 'Bathroom',
                },

            ],
            currentId: '',
        }
    },
    methods: {
        activeTag(item) {
            if (this.currentId === '') {
                this.currentId = this.articlesData[0].id;
            }
            if (item.id !== this.currentId) {
                this.articlesData.find(obj => obj.id === this.currentId).isActive = false;
                item.isActive = true;
                this.currentId = item.id;
            }
        },
    },
};
</script>

<style lang="scss"></style>