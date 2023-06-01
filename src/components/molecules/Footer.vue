<!-- bg-[#F9FFF7] -->
<template>
  <footer class="footer">
    <div class="footer__container">
      <div class="footer__profile">
        <img
          src="@/assets/images/logo.png"
          alt="logo"
          width="250"
          height="50"
          class="footer__profile__logo" />
        <p class="footer__profile__address">
          Jl. Prof. DR. Satrio No.7, RT.3/RW.3, Karet Kuningan, Kecamatan
          Setiabudi, Kota Jakarta Selatan,<br />
          Daerah Khusus Ibukota Jakarta 12950
        </p>
        <div class="footer__wrapper_icon">
          <div class="footer__icon">
            <img
              src="@/assets/icons/mail.png"
              alt="icon"
              class="footer__icon__item" />
          </div>
          <div class="footer__icon">
            <img
              src="@/assets/icons/phone.png"
              alt="icon"
              class="footer__icon__item" />
          </div>
          <div class="footer__icon">
            <img
              src="@/assets/icons/instagram.png"
              alt="icon"
              class="footer__icon__item" />
          </div>
        </div>
      </div>

      <ul class="footer__menu">
        <li>Categories</li>
        <li>Cupcake</li>
        <li>Pizza</li>
        <li>Kebab</li>
        <li>Salmon</li>
        <li>Dougnut</li>
      </ul>

      <ul class="footer__menu">
        <li>About Us</li>
        <li>About Us</li>
        <li>FAQ</li>
        <li>Report Problem</li>
      </ul>

      <ul class="footer__menu">
        <li>Newsletter</li>
        <li>
          Get now free 50% discount for alll <br />
          products on your first order
        </li>
        <li class="footer__menu__input">
          <input type="email" placeholder="Your email address" />
          <button type="button">SEND</button>
        </li>
        <li>
          <img src="@/assets/icons/mail-fill.png" alt="icon" />
          elemes@gmail.com
        </li>
        <li><img src="@/assets/icons/phone.png" alt="icon" /> 0888 111 222</li>
      </ul>
    </div>
  </footer>
</template>

<script>
export default {
  name: "FooterComponent",
};
</script>

<style scoped>
.footer {
  width: 100%;
  height: fit-content;
  padding: 40px;
  /* position: relative; */
}

.footer__container {
  width: 100%;
  height: fit-content;
  background-color: #f9fff6;
  padding: 50px;
  border-radius: 40px;
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}

.footer__profile {
  width: 40%;
  height: fit-content;
}

.footer__profile__logo {
  width: 250px;
  object-fit: fill;
  margin-bottom: 20px;
}

.footer__profile__address {
  font-family: var(--font-rubik);
  font-weight: 400;
  color: #757575;
}

.footer__wrapper_icon {
  width: fit-content;
  height: fit-content;
  display: flex;
  gap: 10px;
  margin-top: 20px;
}

.footer__icon {
  width: 35px;
  height: 35px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 100%;
  background-color: white;
}

.footer__icon:nth-child(1) {
  background-color: var(--color-primary);
}

.footer__menu {
  width: fit-content;
  height: fit-content;
  padding: 0 30px;
  font-family: var(--font-rubik);
  font-size: 14px;
  font-weight: 400;
  color: #757575;
}

.footer__menu li:nth-child(1) {
  font-weight: 500;
  font-size: 18px;
  margin-bottom: 40px;
  color: #333333;
}

.footer__menu li {
  margin-bottom: 20px;
}

.footer__menu li:hover:not(li:nth-child(1)) {
  color: var(--color-primary);
  cursor: pointer;
}

.footer__menu__input {
  width: 100%;
  height: fit-content;
  height: fit-content;
}

.footer__menu__input input {
  padding: 10px;
  width: 80%;
  height: 40px;
  border: 1px solid black;
  border-right: none;
  border-radius: 10px 0 0 10px;
  font-family: var(--font-rubik);
  font-weight: 400;
}

.footer__menu__input input:focus,
.footer__menu__input button:focus {
  outline: none;
}

.footer__menu__input button {
  width: 20%;
  height: 40px;
  border-top-right-radius: 8px;
  border-bottom-right-radius: 8px;
  border: 1px solid var(--color-primary);
  background-color: var(--color-primary);
  color: white;
  font-family: var(--font-rubik);
  font-weight: 500;
  padding: 5px;
  cursor: pointer;
}

@media screen and (max-width: 550px) {
  .footer {
    padding: 0;
  }

  .footer__menu {
    width: 100%;
  }
  .footer__profile {
    width: 100%;
    margin-bottom: 20px;
  }

  .footer__menu {
    padding: 10px;
  }
}
</style>
