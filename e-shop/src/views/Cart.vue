<template>
  <div class="container">
    <h1 class="heading">Cart</h1>
    <div class="grid" v-if="cart.length > 0">
      <product-list v-for="item of cart" :key="item.id" :data="item">
        <button class="btn" @click="remove(item.id)">Remove</button>
      </product-list>
    </div>
    <div v-else>
      <h1 class="cart">Cart is an empty</h1>
    </div>
  </div>
</template>

<script>
import productList from "../components/productList.vue";
export default {
  components: { productList },

  props: ["cart", "cards"],

  methods: {
    remove(id) {
      this.$emit("remove", id);
    },
  },
};
</script>

<style scoped>
.heading {
  margin-top: 20px;
}

.grid {
  display: grid;
  grid-template-columns: repeat(6, 1fr);
  grid-gap: 30px;
  margin-top: 20px;
}

.heading {
  margin-top: 20px;
}

.btn {
  font-size: 18px;
  padding: 15px;
  background: none;
  border: 2px solid teal;
  border-radius: 10px;
  cursor: pointer;
}

.btn:hover {
  opacity: 0.6;
  background-color: black;
  color: white;
}

.btn:active {
  opacity: 0;
}

.cart {
  color: red;
  font-size: 36px;
  text-align: center;
  margin-top: 20px;
}
</style>