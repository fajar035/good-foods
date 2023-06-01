<template>
  <div class="browse">
    <h1 class="browse__title">
      Browser Our Category <br />
      <span>Receipt</span>
    </h1>
    <div class="browse__card">
      <CardTranding v-for="(item, idx) in trending" :key="idx" :data="item" />
    </div>
    <div class="browse__wrapper__btn">
      <button>ALL Receipt</button>
    </div>
  </div>
</template>

<script>
import CardTranding from "./CardTranding.vue";
import pizzaPaperoni from "@/assets/images/pizza-paperoni.png";
import pizzaMeat from "@/assets/images/pizza-meet.png";
import donerKebab from "@/assets/images/doner-kebab.png";
import salmonRoll from "@/assets/images/salmon-roll.png";
import chupcakeChoco from "@/assets/images/cupcake-choco.png";
import donutMilk from "@/assets/images/donut-milk.png";
import donutUnicorn from "@/assets/images/donut-unicorn.png";
import kathiKebab from "@/assets/images/kathi-kebab.png";

export default {
  name: "BrowseTranding",
  components: {
    CardTranding,
  },
  data: () => ({
    trending: [
      {
        name: "Pizza Paperoni",
        category: "Pizza",
        rating: 4,
        img: pizzaPaperoni,
        bg: "#E6F3F5",
      },
      {
        name: "Pizza Meat",
        category: "Pizza",
        rating: 3,
        img: pizzaMeat,
        bg: "#E6F3F5",
      },
      {
        name: "Doner Kebab",
        category: "Kebab",
        rating: 5,
        img: donerKebab,
        bg: "#EAEEFA",
      },
      {
        name: "Salmon Roll",
        category: "Salmon",
        rating: 4,
        img: salmonRoll,
        bg: "#F9EEF3",
      },
      {
        name: "Cupcake Choco",
        category: "Cupcake",
        rating: 4,
        img: chupcakeChoco,
        bg: "#F0FEEB",
      },
      {
        name: "Doughnut Milk",
        category: "Doughnut",
        rating: 5,
        img: donutMilk,
        bg: "#F3F7D9",
      },
      {
        name: "Doughnut Unicorn",
        category: "Doughnut",
        rating: 4,
        img: donutUnicorn,
        bg: "#F3F7D9",
      },
      {
        name: "Kathi Kebab",
        category: "Kebab",
        rating: 4,
        img: kathiKebab,
        bg: "#EAEEFA",
      },
    ],
  }),
};
</script>

<style scoped>
.browse {
  width: 100%;
  height: fit-content;
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

.browse__card {
  margin: 40px 0;
  width: 100%;
  height: fit-content;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
  flex-wrap: wrap;
}

.browse__wrapper__btn {
  width: 100%;
  height: fit-content;
  display: flex;
  align-items: center;
  justify-content: center;
}

.browse__wrapper__btn button {
  width: 160px;
  height: 50px;
  background-color: var(--color-primary);
  color: white;
  font-family: var(--font-rubik);
  font-weight: 500;
  font-size: 16px;
  border: none;
  border-radius: 100px;
  cursor: pointer;
}

.browse__wrapper__btn bottom:focus {
  outline: none;
}
</style>
