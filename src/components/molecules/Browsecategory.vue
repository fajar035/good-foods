<template>
  <div class="browse">
    <h1 class="browse__title">
      Browser Our Category <br />
      <span>Receipt</span>
    </h1>
    <div class="browse__card">
      <CardCategory :data="category" />
    </div>
  </div>
</template>

<script>
import CardCategory from "./CardCategory.vue";
import cupcake from "@/assets/images/cupcake.png";
import pizza from "@/assets/images/pizza.png";
import kebab from "@/assets/images/kebab.png";
import salmon from "@/assets/images/salmon.png";
import donut from "@/assets/images/donut.png";
import drink from "@/assets/images/drink.png";

export default {
  name: "BrowseCategory",
  components: {
    CardCategory,
  },
  data: () => ({
    category: [
      {
        name: "Cupcake",
        items: 22,
        icon: cupcake,
        bg: "#F0FEEB",
      },
      {
        name: "Pizza",
        items: 25,
        icon: pizza,
        bg: "#E6F3F5",
      },
      {
        name: "Kebab",
        items: 12,
        icon: kebab,
        bg: "#F9EEF3",
      },
      {
        name: "Salmon",
        items: 22,
        icon: salmon,
        bg: "#F9EEF3",
      },
      {
        name: "Doughnut",
        items: 11,
        icon: donut,
        bg: "#F3F7D9",
      },
      {
        name: "Drink",
        items: 20,
        icon: drink,
        bg: "#F0FEEB",
      },
    ],
  }),
};
</script>

<style scoped>
.browse {
  width: 100%;
  height: 573px;
  padding: var(--padding-default);
}

.browse__title {
  font-family: var(--font-rubik);
  font-weight: 500;
  font-size: 38px;
  color: #333333;
}

.browse__title span {
  color: var(--color-primary);
}
</style>
