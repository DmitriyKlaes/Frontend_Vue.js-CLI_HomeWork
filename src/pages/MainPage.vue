<template>
    <main>
        <section class="promo">
            <article class="promo__info">
                <h2 class="promo__head">Let Your Home Be Unique</h2>
                <p class="promo__text">There are many variations of the passages of
                    lorem Ipsum fromavailable, majority.</p>
                <a href="#" class="promo__link">
                    <div class="promo__button">
                        Get Started
                        <svg width="19" height="17" viewBox="0 0 19 17" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path d="M2 8.43542L15.7232 8.29857M10.6182 1.91138L17.1412 8.43436L10.4868 15.0887"
                                stroke="#CDA274" stroke-width="2" stroke-linecap="square" stroke-linejoin="round" />
                        </svg>
                    </div>
                </a>
            </article>
        </section>
        <section class="top">
            <h2 class="top__head">Follow Our Projects</h2>
            <p class="top__text">It is a long established fact that a reader will be distracted by the of readable content
                of page lookings at its layouts points.</p>
            <div class="top__content">
                <div class="top__item">
                    <img class="top__img" src="@/assets/img/top-image1.png" alt="top-image">
                    <article class="top__description">
                        <div class="top__text-container">
                            <h3 class="top__heading">Modern Kitchan</h3>
                            <p class="top__text-item">Decor / Artchitecture</p>
                        </div>
                        <a href="#" class="top__link">
                            <div class="top__button">
                                <svg width="70" height="70" viewBox="0 0 70 70" fill="none"
                                    xmlns="http://www.w3.org/2000/svg">
                                    <circle cx="35" cy="35" r="35" fill="#F4F0EC" />
                                    <path d="M32 44L40 35L32 26" stroke="#292F36" stroke-width="2" stroke-linecap="round"
                                        stroke-linejoin="round" />
                                </svg>
                            </div>
                        </a>
                    </article>
                </div>
                <div class="top__item">
                    <img class="top__img" src="@/assets/img/top-image2.png" alt="top-image">
                    <article class="top__description">
                        <div class="top__text-container">
                            <h3 class="top__heading">Modern Kitchan</h3>
                            <p class="top__text-item">Decor / Artchitecture</p>
                        </div>
                        <a href="#" class="top__link">
                            <div class="top__button">
                                <svg width="70" height="70" viewBox="0 0 70 70" fill="none"
                                    xmlns="http://www.w3.org/2000/svg">
                                    <circle cx="35" cy="35" r="35" fill="#F4F0EC" />
                                    <path d="M32 44L40 35L32 26" stroke="#292F36" stroke-width="2" stroke-linecap="round"
                                        stroke-linejoin="round" />
                                </svg>
                            </div>
                        </a>
                    </article>
                </div>
                <div class="top__item">
                    <img class="top__img" src="@/assets/img/top-image3.png" alt="top-image">
                    <article class="top__description">
                        <div class="top__text-container">
                            <h3 class="top__heading">Modern Kitchan</h3>
                            <p class="top__text-item">Decor / Artchitecture</p>
                        </div>
                        <a href="#" class="top__link">
                            <div class="top__button">
                                <svg width="70" height="70" viewBox="0 0 70 70" fill="none"
                                    xmlns="http://www.w3.org/2000/svg">
                                    <circle cx="35" cy="35" r="35" fill="#F4F0EC" />
                                    <path d="M32 44L40 35L32 26" stroke="#292F36" stroke-width="2" stroke-linecap="round"
                                        stroke-linejoin="round" />
                                </svg>
                            </div>
                        </a>
                    </article>
                </div>
                <div class="top__item">
                    <img class="top__img" src="@/assets/img/top-image4.png" alt="top-image">
                    <article class="top__description">
                        <div class="top__text-container">
                            <h3 class="top__heading">Modern Kitchan</h3>
                            <p class="top__text-item">Decor / Artchitecture</p>
                        </div>
                        <a href="#" class="top__link">
                            <div class="top__button">
                                <svg width="70" height="70" viewBox="0 0 70 70" fill="none"
                                    xmlns="http://www.w3.org/2000/svg">
                                    <circle cx="35" cy="35" r="35" fill="#F4F0EC" />
                                    <path d="M32 44L40 35L32 26" stroke="#292F36" stroke-width="2" stroke-linecap="round"
                                        stroke-linejoin="round" />
                                </svg>
                            </div>
                        </a>
                    </article>
                </div>
            </div>
        </section>
        <section class="about">
            <div class="about__container">
                <article class="about__item">
                    <h2 class="about__heading">12</h2>
                    <p class="about__text">Years Of Experiance</p>
                </article>
                <img src="@/assets/img/line.png" alt="line" class="about__line">
                <article class="about__item">
                    <h2 class="about__heading">85</h2>
                    <p class="about__text">Success Project</p>
                </article>
                <img src="@/assets/img/line.png" alt="line" class="about__line">
                <article class="about__item">
                    <h2 class="about__heading">15</h2>
                    <p class="about__text">Active Project</p>
                </article>
                <img src="@/assets/img/line.png" alt="line" class="about__line">
                <article class="about__item">
                    <h2 class="about__heading">95</h2>
                    <p class="about__text">Happy Customers</p>
                </article>
            </div>
        </section>
        <section class="bottom">
            <h2 class="bottom__head">Articles & News</h2>
            <p class="bottom__text">It is a long established fact that a reader will be distracted by the of readable
                content
                of a page when lookings at its layouts the points of using.</p>
            <div class="bottom__content" id="app">
                <article class="bottom__item" v-for="item in firstArrayElements(3)" :key="item.src">
                    <div class="bottom__img-box">
                        <img class="bottom__img" :src=item.src alt="bottom-image">
                        <div class="bottom__inside">
                            <p class="bottom__inside-text">{{ item.insideText }}</p>
                        </div>
                    </div>
                    <h3 class="bottom__heading">{{ item.heading }}</h3>
                    <div class="bottom__link-container">
                        <p class="bottom__date">{{ item.date }}</p>
                        <a href="#" class="bottom__link">
                            <div class="bottom__button">
                                <svg width="52" height="53" viewBox="0 0 52 53" fill="none"
                                    xmlns="http://www.w3.org/2000/svg">
                                    <circle cx="26" cy="26.267" r="26" fill="#F4F0EC" />
                                    <path d="M23.7714 32.9527L29.7143 26.267L23.7714 19.5813" stroke="#292F36"
                                        stroke-width="2" stroke-linecap="round" stroke-linejoin="round" />
                                </svg>
                            </div>
                        </a>
                    </div>
                </article>
            </div>
        </section>
    </main>
</template>

<script>

export default {
    name: 'MainPage',
    data() {
        return {
            items: [
                {
                    src: require('@/assets/img/bottom-image1.png'),
                    insideText: "Kitchan Design",
                    heading: "Let’s Get Solution For Building Construction Work",
                    date: "30 july, 2023"
                },
                {
                    src: require('@/assets/img/bottom-image2.png'),
                    insideText: "Living Design",
                    heading: "Low Cost Latest Invented Interior Designing Ideas.",
                    date: "30 july, 2023"
                },
                {
                    src: require('@/assets/img/bottom-image3.png'),
                    insideText: "Interior Design",
                    heading: "Best For Any Office & Business Interior Solution",
                    date: "30 july, 2023"
                },
                {
                    src: require('@/assets/img/bottom-image4.png'),
                    insideText: "Kitchan Design",
                    heading: "Let’s Get Solution For Building Construction Work",
                    date: "30 july, 2023"
                },
                {
                    src: require('@/assets/img/bottom-image5.png'),
                    insideText: "Living Design",
                    heading: "Low Cost Latest Invented Interior Designing Ideas.",
                    date: "30 july, 2023"
                },
                {
                    src: require('@/assets/img/bottom-image6.png'),
                    insideText: "Interior Design",
                    heading: "Best For Any Office & Business Interior Solution",
                    date: "30 july, 2023"
                },
            ],
        }
    },
    methods: {
        firstArrayElements(number) {
            return this.items.slice(0, number);
        }
    },
};
</script>

<style lang="scss"></style>