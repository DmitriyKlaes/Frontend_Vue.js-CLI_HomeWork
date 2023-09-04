<template>
  <div>
    <header class="header">
      <div class="header__name">
        <router-link to="/" class="header__logo">
          <svg
            viewBox="0 0 34 34"
            width="34"
            height="34"
            fill="none"
            xmlns="http://www.w3.org/2000/svg">
            <path
              d="M0 34.0003H13.4588V24.499C13.4588 22.4853 15.0898 20.8543 17.1035 20.8543C19.1172 20.8543 20.7482 22.4853 20.7482 24.499V34.0003H33.9975V0C15.2211 0 0 15.2211 0 34.0003Z"
              fill="#CDA274"></path>
          </svg>
        </router-link>
        <div class="header__head">Interno</div>
      </div>
      <div class="header__nav">
        <router-link to="/" class="header__link">Home</router-link>
        <router-link to="/project" class="header__link">Project</router-link>
        <router-link to="/blog" class="header__link">Blog</router-link>
      </div>
    </header>
  </div>
</template>

<script>
export default {
  name: 'Header',
};
</script>

<style lang="scss">
@import '@/assets/styles/_mixins.scss';
@import '@/assets/styles/_vars.scss';
@import '@/assets/styles/text-style.scss';

.header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding-top: 50px;
  max-width: $siteWidth;
  margin: 0 auto;

  &__name {
    display: flex;
    align-items: center;
    gap: 10px;
  }

  &__logo {
    height: 34px;
    width: 34px;
  }

  &__head {
    @include fontStyle(40px, $textColor);
  }

  &__nav {
    display: flex;
    justify-content: space-between;
    width: 240px;
  }

  &__link {
    font-family: $smallTextFont;
    text-align: center;
    @include fontStyle(20px, $textColor);
  }
}
</style>
