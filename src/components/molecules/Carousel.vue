<template>
  <div class="carousel">
    <div class="carousel__about">
      <h1>Good Food Us Good Mood</h1>
      <div class="carousel__image" v-if="width <= 768">
        <img
          src="@/assets/images/salad-tomato.png"
          alt="salad"
          class="carousel__image__banner" />
        <div
          :class="`carousel__card ${width <= 768 ? 'card__responsive' : ''}`">
          <img
            src="@/assets/images/salad-tomato.png"
            alt="salad"
            class="carousel__card__thumbnail" />
          <div class="carousel__card__detail">
            <p>Green Salad Tomato</p>
            <p>Tomato</p>
            <div class="carousel__card__rating">
              <img src="@/assets/icons/star-fill.png" alt="star" class="icon" />
              <img src="@/assets/icons/star-fill.png" alt="star" class="icon" />
              <img src="@/assets/icons/star-fill.png" alt="star" class="icon" />
              <img src="@/assets/icons/star-fill.png" alt="star" class="icon" />
              <img src="@/assets/icons/star.png" alt="star" class="icon" />
            </div>
          </div>
        </div>
      </div>
      <p>
        I would think that conserving our natural resources should be a
        conservative position: Not to waste food, and not to throw away a lot of
        the food that we buy.
      </p>
      <button type="button">Daftar Sekarang</button>
      <button type="button">About Us</button>
    </div>
    <div class="carousel__image" v-if="width > 768">
      <img
        src="@/assets/images/salad-tomato.png"
        alt="salad"
        class="carousel__image__banner" />
      <div class="carousel__card">
        <img
          src="@/assets/images/salad-tomato.png"
          alt="salad"
          class="carousel__card__thumbnail" />
        <div class="carousel__card__detail">
          <p>Green Salad Tomato</p>
          <p>Tomato</p>
          <div class="carousel__card__rating">
            <img src="@/assets/icons/star-fill.png" alt="star" class="icon" />
            <img src="@/assets/icons/star-fill.png" alt="star" class="icon" />
            <img src="@/assets/icons/star-fill.png" alt="star" class="icon" />
            <img src="@/assets/icons/star-fill.png" alt="star" class="icon" />
            <img src="@/assets/icons/star.png" alt="star" class="icon" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { useWindowSize } from "@vueuse/core";
const { width } = useWindowSize();
export default {
  name: "CarouselComponent",
  data: () => ({
    width,
  }),
};
</script>

<style scoped>
.carousel {
  width: 100%;
  height: 100vh;
  position: relative;
  background: linear-gradient(
      0deg,
      rgb(255, 255, 255, 0.9),
      rgba(255, 255, 255, 0.9)
    ),
    url(@/assets/images/banner.png);
  background-size: fill;
  background-repeat: no-repeat;
  display: flex;
  align-items: center;
  justify-content: center;
}

.carousel__about {
  width: 50%;
  height: fit-content;
}

.carousel__image {
  width: auto;
  height: auto;
  position: relative;
}

.carousel__about {
  padding: 50px;
  font-family: var(--font-rubik);
}

.carousel__about h1 {
  font-weight: 500;
  font-size: 64px;
  margin-bottom: 40px;
  color: var(--color-primary);
}

.carousel__about p {
  font-weight: 400;
  font-size: 18px;
  margin-bottom: 40px;
  color: #757575;
}

.carousel button {
  padding: 10px 18px;
  margin-right: 20px;
  border-radius: 100px;
  border: none;
  font-family: var(--font-rubik);
  font-size: 14px;
  font-weight: 500;
  color: #333333;
  cursor: pointer;
}

.carousel button:nth-child(3) {
  background-color: var(--color-primary);
  color: white;
}

.carousel__image__banner {
  width: 500px;
  height: 450px;
  border-radius: 100%;
  padding: 30px;
  background-color: rgb(196, 196, 196, 0.2);
  object-fit: fill;
}

.carousel__card {
  width: 292px;
  height: 93px;
  background: rgba(255, 255, 255, 0.74);
  box-shadow: 0px 11px 39px rgba(0, 0, 0, 0.07);
  backdrop-filter: blur(5.5px);
  border-radius: 17px;
  position: absolute;
  bottom: 10px;
  left: -50px;
  display: flex;
  align-items: center;
}

.card__responsive {
  left: 8rem;
  bottom: -10px;
  width: 270px;
}

.carousel__card__thumbnail {
  width: 53px;
  height: 53px;
  object-fit: fill;
  margin: 0 20px;
}

.carousel__card__detail p {
  font-family: var(--font-open);
}

.carousel__card__detail p:nth-child(1) {
  font-size: 14px;
  font-weight: 600;
  color: black;
}

.carousel__card__detail p:nth-child(2) {
  font-size: 12px;
  font-weight: 400;
  color: #757575;
}

.carousel__card__rating {
  width: max-content;
  height: fit-content;
  /* background-color: red; */
  display: flex;
}

.icon {
  width: 15px;
  height: 15px;
  margin-top: 10px;
  object-fit: fill;
}

@media screen and (max-width: 768px) {
  .carousel {
    flex-direction: column;
    padding-top: 5rem;
    height: fit-content;
    width: 100%;
  }
  .carousel__about,
  .carousel__image {
    width: 100%;
  }

  .carousel__card__detail p {
    margin: 0;
  }
}

@media screen and (max-width: 768px) {
  .carousel {
    background-size: contain;
    background-repeat: repeat;
  }
  .carousel__image {
    margin-bottom: 50px;
  }
  .carousel__image__banner {
    width: 400px;
    height: 350px;
  }

  .carousel__about h1 {
    font-size: 50px;
  }

  .carousel button:nth-child(4) {
    background-color: var(--color-primary);
    color: white;
  }
}
</style>
