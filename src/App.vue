<template>
  <Header />
  <MainPage />
  <Blog />
  <BlogDetails />
  <Footer />
</template>

<script>
import Header from '@/components/Header.vue'
import Footer from '@/components/Footer.vue'
import MainPage from '@/pages/MainPage.vue'
import Blog from '@/pages/Blog.vue'
import BlogDetails from '@/pages/BlogDetails.vue'

export default {
  name: 'App',
  components: {
    Header,
    Footer,
    MainPage,
    Blog,
    BlogDetails
  }
}
</script>

<style lang="scss">

</style>
