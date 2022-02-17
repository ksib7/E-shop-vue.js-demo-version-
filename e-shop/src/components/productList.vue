<template>
  <section class="cards">
    <h2>{{ data.title }}</h2>
    <div class="cards__price">Price: {{ data.price }}</div>
    <slot></slot>
  </section>
</template>

<script>
export default {
  props: ["data"],
};
</script>

<style lang="scss" scoped>
.cards {
  max-width: 200px;
  min-height: 250px;
  border: 2px solid black;
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-around;
}

.cards h2 {
  font-size: 36px;
}

.cards__price {
  font-size: 28px;
}
</style>