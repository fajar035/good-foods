<template>
  <Layout>
    <Carousel />
  </Layout>
</template>

<script>
import Layout from "@/components/molecules/Layout.vue";
import Carousel from "./components/molecules/Carousel.vue";

export default {
  name: "AppView",
  components: {
    Layout,
    Carousel,
  },
};
</script>
