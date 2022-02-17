<template>
  <div class="container">
    <h1 class="heading">Home</h1>
    <div class="grid">
      <product-list v-for="item of cards" :key="item.id" :data="item">
        <button class="btn" @click="buy(item.id)">Add</button>
      </product-list>
    </div>
  </div>
</template>

<script>
import productList from "../components/productList.vue";
export default {
  components: { productList },

  props: ["cards", "cart"],

  methods: {
    buy(id) {
      this.$emit("add", id);
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
  margin: 20px auto;
}

.btn {
  font-size: 18px;
  padding: 15px 40px;
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
</style>