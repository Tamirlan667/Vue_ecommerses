<template>
  <header class="header">
    <div class="logo">
      <router-link to="/">
        <img src="@/assets/logo.png" alt="Logo" />
      </router-link>
    </div>

    <nav>
      <ul>
        <li><router-link to="/home">Home</router-link></li>
        <li><router-link to="/about">About</router-link></li>
        <li><router-link to="/products">Products</router-link></li>
      </ul>
    </nav>

    <ul>
      <li>
        <base-button-with-badge
          :quantity="totalLikes"
          @click="openModal('likesModal')"
        >
          <like-icon></like-icon>
        </base-button-with-badge>
      </li>

      <li>
        <base-button-with-badge
          :quantity="cartTotalProductsQuantity"
          @click="openModal('cartModal')"
        >
          <cart-icon></cart-icon>
        </base-button-with-badge>
      </li>
    </ul>
  </header>
</template>

<script>
import { mapActions, mapGetters } from "vuex";
import CartIcon from "./icons/CartIcon.vue";
import LikeIcon from "./icons/LikeIcon.vue";
import BaseButtonWithBadge from "./UI/Buttons/BaseButtonWithBadge.vue";

export default {
  components: { CartIcon, LikeIcon, BaseButtonWithBadge },

  methods: {
    ...mapActions(["openModal"]),
  },
  computed: {
    ...mapGetters(["cartTotalProductsQuantity", "totalLikes"]),
  },
};
</script>

<style scoped>
.header {
  display: grid;
  gap: 20px;
  grid-template-columns: auto 1fr auto; /* Добавлено для логотипа и навигации */
  padding: 200px 20px;
  align-items: center;
  background-color: #fff; /* Можно добавить фон для визуального разделения */
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1); /* Добавлено для тени */
}

.logo img {
  height: 50px; /* Размер логотипа */
}

nav {
  display: flex;
  justify-content: center;
}

nav ul {
  display: flex;
  gap: 25px;
  list-style: none;
  padding: 0;
}

nav ul li a {
  text-decoration: none;
  color: #333; /* Цвет ссылок */
  transition: color 0.3s;
}

nav ul li a:hover {
  color: #007bff; /* Цвет при наведении */
}

ul {
  display: flex;
  justify-content: flex-end;
  gap: 25px;
  align-items: center;
  list-style: none;
  padding: 0;
}

@media screen and (min-width: 768px) {
  .header {
    padding: 0;
  }
}
</style>
