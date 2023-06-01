<template>
  <Layout>
    <Carousel />
    <Browsecategory />
    <BrowseTranding />
  </Layout>
</template>

<script>
import Layout from "@/components/molecules/Layout.vue";
import Carousel from "./components/molecules/Carousel.vue";
import Browsecategory from "./components/molecules/Browsecategory.vue";
import BrowseTranding from "./components/molecules/BrowseTranding.vue";

export default {
  name: "AppView",
  components: {
    Layout,
    Carousel,
    Browsecategory,
    BrowseTranding,
  },
};
</script>
