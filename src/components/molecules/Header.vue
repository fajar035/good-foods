<template>
  <nav :class="`navbar ${scrollY >= 90 ? 'on-scroll' : ''}`">
    <img src="@/assets/images/logo.png" alt="logo" class="navbar__logo" />
    <ul class="navbar__menu">
      <li>Home</li>
      <li>About</li>
      <li>Promotions</li>
      <li>Blogs</li>
      <li>Contact Us</li>
    </ul>
    <div class="navbar__auth">
      <button>Masuk</button>
      <button>Daftar Sekarang</button>
    </div>
  </nav>
</template>

<script>
export default {
  name: "HeaderComponent",
  data: () => ({
    scrollY: 0,
  }),
  mounted() {
    window.addEventListener("scroll", this.onScroll);
  },
  unmounted() {
    window.removeEventListener("scroll", this.onScroll);
  },
  methods: {
    onScroll(e) {
      this.scrollY = e.target.documentElement.scrollTop;
    },
  },
};
</script>

<style scoped>
.navbar {
  width: 100%;
  height: 80px;
  padding-left: var(--padding-default);
  padding-right: var(--padding-default);
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: transparent;
  position: fixed;
  top: 0;
  z-index: 10;
  transition: 0.3s;
}

.on-scroll {
  background-color: white;
  box-shadow: rgba(99, 99, 99, 0.2) 0px 2px 8px 0px;
}

.navbar__menu {
  display: flex;
  gap: 40px;
  font-family: var(--font-rubik);
  font-weight: 500;
  font-size: 14px;
  color: #757575;
  cursor: pointer;
}

.navbar__menu li {
  width: max-content;
  height: fit-content;
}

.navbar__menu li:nth-child(3) {
  position: relative;
}
.navbar__menu li:nth-child(3)::after {
  content: "HOT";
  position: absolute;
  top: -20px;
  right: -10px;
  background-color: #e7462d;
  color: white;
  font-size: 10px;
  border-radius: 8px;
  padding: 3px 5px;
}
.navbar__menu li:hover {
  color: var(--color-primary);
}

.navbar__auth {
  width: fit-content;
  height: fit-content;
  display: flex;
}

.navbar__auth button {
  margin: 10px;
  width: 147px;
  height: 42px;
  border-radius: 100px;
  border: none;
  font-family: var(--font-rubik);
  font-weight: 500;
  font-size: 14px;
  cursor: pointer;
}
.navbar__auth button:nth-child(1) {
  background-color: transparent;
  color: #333333;
}

.navbar__auth button:nth-child(2) {
  background-color: var(--color-primary);
  color: white;
}

@media screen and (max-width: 1020px) {
  .navbar {
    padding: 20px;
  }

  .navbar__logo {
    width: 150px;
    height: 50px;
    object-fit: contain;
  }
  .navbar__menu {
    display: none;
  }

  .navbar__auth button:nth-child(1) {
    display: none;
  }
}

/* @media screen and (max-width: 1020px) {
  .navbar {
    display: none;
  }
} */
</style>
