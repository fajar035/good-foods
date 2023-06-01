<template>
  <div class="navbar">
    <ul :class="`navbar__menu_item ${isOpenMenu ? 'open' : ''}`">
      <li>About</li>
      <li>Blogs</li>
      <li>Contact Us</li>
      <li>Masuk</li>
    </ul>
    <div class="navbar__menu">
      <img
        src="@/assets/icons/menu.png"
        alt="menu"
        class="navbar__menu__icon" />
      <p>Home</p>
    </div>
    <div class="navbar__menu">
      <img
        src="@/assets/icons/menu.png"
        alt="menu"
        class="navbar__menu__icon" />
      <p>Promotions</p>
    </div>
    <div class="navbar__menu" @click="handleOthers">
      <img
        src="@/assets/icons/menu.png"
        alt="menu"
        class="navbar__menu__icon" />
      <p>Others</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "NavbarComponent",
  data: () => ({
    isOpenMenu: false,
  }),
  methods: {
    handleOthers() {
      this.isOpenMenu = !this.isOpenMenu;
    },
  },
};
</script>

<style scoped>
.navbar {
  width: 100%;
  height: 70px;
  display: flex;
  justify-content: space-around;
  align-items: center;
  position: fixed;
  bottom: 0;
  background-color: white;
  border: 1px solid #f8f8f8;
}

.navbar__menu {
  text-align: center;
  cursor: pointer;
}

.navbar__menu_item {
  width: 100%;
  height: max-content;
  padding: 20px;
  text-align: center;
  position: absolute;
  transform: translateY(0);
  visibility: hidden;
  background-color: var(--color-primary);
  transition: 0.3s;
  display: flex;
  flex-direction: column;
  gap: 20px;
  font-family: var(--font-rubik);
  font-weight: 400;
  color: white;
  border-radius: 10px;
  cursor: pointer;
}

.navbar__menu_item:hover {
  color: red;
}

.navbar__menu_item::after {
  content: "";
  border-width: 10px;
  border-style: solid;
  border-color: var(--color-primary) transparent transparent transparent;
  position: absolute;
  bottom: -18px;
  right: 55px;
  transform: rotate(360deg);
}

.open {
  transform: translateY(-7.7rem);
  visibility: visible;
}
</style>
