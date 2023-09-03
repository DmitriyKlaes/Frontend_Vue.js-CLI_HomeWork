<template>
  <Header />
  <ProductDetails />
  <MainPage />
  <Blog />
  <BlogDetails />
  <Project />
  <ProjectDetails />
  <Footer />
</template>

<script>
import Header from '@/components/Header.vue';
import Footer from '@/components/Footer.vue';
import MainPage from '@/pages/MainPage.vue';
import Blog from '@/pages/Blog.vue';
import BlogDetails from '@/pages/BlogDetails.vue';
import ProductDetails from '@/components/HW-23-07-31/ProductDetails.vue';
import Project from './pages/Project.vue';
import ProjectDetails from './pages/ProjectDetails.vue';

export default {
  name: 'App',
  components: {
    Header,
    Footer,
    MainPage,
    Blog,
    BlogDetails,
    ProductDetails,
    Project,
    ProjectDetails,
  },
};
</script>

<style lang="scss"></style>
