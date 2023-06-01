<template>
  <div class="carousel">
    <div class="inner" ref="inner" :style="innerStyles">
      <div
        class="card"
        v-for="({ name, icon, items, bg }, idx) in data"
        :key="idx"
        :style="{ backgroundColor: bg }">
        <img :src="icon" alt="icon" width="40" class="card__img" />
        <p class="card__title">{{ name }}</p>
        <p class="card__item">{{ items }} items</p>
      </div>
    </div>
  </div>
  <div class="wrapper-btn">
    <button class="btn" @click="prev">
      <span>
        <img src="@/assets/icons/Chevron-Left.png" alt="icon" />
      </span>
      prev
    </button>
    <button class="btn" @click="next">
      next
      <span>
        <img src="@/assets/icons/Chevron-Right.png" alt="icon" />
      </span>
    </button>
  </div>
</template>

<script>
export default {
  name: "CardComponent",
  props: ["data"],
  data() {
    return {
      cards: this.data,
      innerStyles: {},
      step: "",
      transitioning: false,
    };
  },

  mounted() {
    this.setStep();
    this.resetTranslate();
  },

  methods: {
    setStep() {
      const innerWidth = this.$refs.inner.scrollWidth;
      const totalCards = this.cards.length;
      this.step = `${innerWidth / totalCards}px`;
    },

    next() {
      if (this.transitioning) return;

      this.transitioning = true;

      this.moveLeft();

      this.afterTransition(() => {
        const card = this.cards.shift();
        this.cards.push(card);
        this.resetTranslate();
        this.transitioning = false;
      });
    },

    prev() {
      if (this.transitioning) return;

      this.transitioning = true;

      this.moveRight();

      this.afterTransition(() => {
        const card = this.cards.pop();
        this.cards.unshift(card);
        this.resetTranslate();
        this.transitioning = false;
      });
    },

    moveLeft() {
      this.innerStyles = {
        transform: `translateX(-${this.step})
                    translateX(-${this.step})`,
      };
    },

    moveRight() {
      this.innerStyles = {
        transform: `translateX(${this.step})
                    translateX(-${this.step})`,
      };
    },

    afterTransition(callback) {
      const listener = () => {
        callback();
        this.$refs.inner.removeEventListener("transitionend", listener);
      };
      this.$refs.inner.addEventListener("transitionend", listener);
    },

    resetTranslate() {
      this.innerStyles = {
        transition: "none",
        transform: `translateX(-${this.step})`,
      };
    },
  },
};
</script>

<style>
.carousel {
  width: 100%;
  height: fit-content;
  overflow: hidden;
}

.inner {
  transition: transform 0.2s;
  white-space: nowrap;
  padding: 50px;
}

.card {
  width: 230px;
  height: 173px;
  margin-right: 10px;
  display: inline-flex;
  flex-direction: column;
  color: white;
  border-radius: 4px;
  align-items: center;
  justify-content: center;
  gap: 10px;
  cursor: pointer;
}

.card__img {
  margin-bottom: 10px;
}

.card__title {
  font-family: var(--font-rubik);
  font-weight: 500;
  font-size: 16px;
  color: #333333;
}

.card__item {
  font-family: var(--font-rubik);
  font-weight: 400;
  font-size: 16px;
  color: #333333;
}

.wrapper-btn {
  width: 100%;
  height: fit-content;
  display: flex;
  justify-content: flex-end;
  gap: 20px;
}

.btn {
  width: 113px;
  height: 50px;
  border: none;
  border-radius: 100px;
  cursor: pointer;
  position: relative;
  background-color: var(--color-primary);
  color: white;
  font-family: var(--font-rubik);
  font-weight: 500;
  font-size: 16px;
  display: flex;
  align-items: center;
}

.btn:nth-child(2) {
  padding-left: 20px;
}

.btn span {
  width: 40px;
  height: 40px;
  background-color: white;
  border-radius: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 10px;
}

.btn span img {
  width: 10px;
  height: 10px;
}
</style>
