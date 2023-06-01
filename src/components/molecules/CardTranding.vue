<template>
  <div class="card" :style="{ backgroundColor: data.bg }">
    <img :src="data.img" alt="food-img" class="card__img" />
    <p class="card__title">{{ data.name }}</p>
    <p class="card__category">{{ data.category }}</p>
    <div class="card__wrapper__icon">
      <img :src="iconFill" alt="star" v-for="n in data.rating" :key="n" />
      <img :src="icon" alt="star" v-for="n in 5 - data.rating" :key="n" />
    </div>
  </div>
</template>

<script>
import starFill from "@/assets/icons/star-fill.png";
import star from "@/assets/icons/star.png";

export default {
  name: "CardTranding",
  props: ["data"],
  data: () => ({
    iconFill: starFill,
    icon: star,
  }),
};
</script>

<style scoped>
.card {
  width: 287px;
  height: 306px;
  background-color: blue;
  margin: 20px 0;
  display: block;
  padding: 40px 20px;
}

.card__img {
  border-radius: 6px;
}

.card__title {
  font-family: var(--font-rubik);
  font-size: 26px;
  font-weight: 500;
  color: black;
}

.card__category {
  font-family: var(--font-rubik);
  font-size: 18px;
  font-weight: 500;
  color: var(--color-primary);
}

.card__wrapper__icon {
  width: fit-content;
  height: fit-content;
  display: flex;
  align-items: center;
  margin: 20px 0;
}
</style>
