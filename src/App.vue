<template>
  <Layout>
    <div class="carousel"></div>
  </Layout>
</template>

<script>
import Layout from "@/components/molecules/Layout.vue";

export default {
  name: "AppView",
  components: {
    Layout,
  },
};
</script>

<style scoped>
.carousel {
  width: 100%;
  /* height: calc(100% - 50px); */
  height: 1000px;
}
</style>
