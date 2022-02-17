<template>
  <div class="container">
    <nav-header></nav-header>
    <router-view
      :cards="cards"
      :cart="cart"
      @add="addToCart"
      @remove="removeFromCart"
    />
  </div>
</template>

<script>
import navHeader from "./components/navHeader.vue";
export default {
  components: { navHeader },

  data() {
    return {
      cards: [],
      cart: [],
    };
  },

  methods: {
    addToCart(id) {
      const items = this.cards.find((item) => item.id == id);
      this.cart.push(items);
      window.localStorage.setItem("cart-products", JSON.stringify(this.cart));
    },

    removeFromCart(id) {
      const indx = this.cart.find((item) => item.id == id);
      this.cart.splice(indx, 1);
      window.localStorage.setItem("cart-products", JSON.stringify(this.cart));
    },
  },

  mounted() {
    this.cards = [
      { id: 1, title: "Shirt", price: 80 },
      { id: 2, title: "Trousers", price: 10 },
      { id: 3, title: "T-Shirt", price: 20 },
      { id: 4, title: "Sweater", price: 40 },
      { id: 5, title: "Jacket", price: 90 },
      { id: 6, title: "Shorts", price: 110 },
      { id: 7, title: "Underwear", price: 800 },
      { id: 8, title: "Pants", price: 340 },
      { id: 9, title: "Hat", price: 190 },
      { id: 10, title: "Cap", price: 1110 },
      { id: 11, title: "Tie", price: 60 },
      { id: 12, title: "Scarf", price: 99 },
    ];

    this.cart = JSON.parse(window.localStorage.getItem("cart-products")) || [];
  },
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.container {
  width: 100%;
  padding: 0 10px;
  margin: 0 auto;
}
</style>