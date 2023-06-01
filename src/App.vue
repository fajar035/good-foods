<template>
  <Layout>
    <Carousel />
    <Browsecategory />
  </Layout>
</template>

<script>
import Layout from "@/components/molecules/Layout.vue";
import Carousel from "./components/molecules/Carousel.vue";
import Browsecategory from "./components/molecules/Browsecategory.vue";

export default {
  name: "AppView",
  components: {
    Layout,
    Carousel,
    Browsecategory,
  },
};
</script>
