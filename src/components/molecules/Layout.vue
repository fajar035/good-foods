<template>
  <Header />
  <slot />
  <Footer />
  <p class="text">© 2021 Elemes id. All rights reserved</p>
  <Navbar v-if="width <= 1020" />
</template>

<script>
import Header from "@/components/molecules/Header.vue";
import Footer from "@/components/molecules/Footer.vue";
import Navbar from "@/components/molecules/Navbar.vue";

import { useWindowSize } from "@vueuse/core";
const { width } = useWindowSize();

export default {
  name: "LayoutPage",
  components: {
    Header,
    Navbar,
    Footer,
  },
  data: () => ({
    width,
  }),
};
</script>

<style scoped>
.text {
  text-align: center;
  font-family: var(--font-rubik);
  font-size: 12px;
  line-height: 16px;
  font-weight: 400;
  color: #757575;
  margin: 20px;
}
</style>
