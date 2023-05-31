<template>
  <Navbar />
  <slot/>
  <Footer />
</template>

<script>
import Navbar from '@/components/molecules/Navbar.vue'
import Footer from '@/components/molecules/Footer.vue'

export default {
  name: 'LayoutPage',
  components: {
    Navbar,
    Footer
  }
}
</script>