<template>
  <header class="header">
    <div class="container container--flex">
      <router-link class="header_h1" to="/">Shop</router-link>
      <nav>
        <router-link class="header__text" to="/">Home</router-link>
        <router-link class="header__text" to="/cart">Cart</router-link>
      </nav>
    </div>
  </header>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.header {
  width: 100%;
  min-height: 65px;
  -webkit-box-shadow: 15px 15px 15px 0px rgba(38, 66, 87, 0.2);
  -moz-box-shadow: 15px 15px 15px 0px rgba(38, 66, 87, 0.2);
  box-shadow: 15px 15px 15px 0px rgba(38, 66, 87, 0.2);
}

.header_h1 {
  font-size: -webkit-xxx-large;
  text-decoration: none;
  color: black;
}

.container--flex {
  display: flex;
  align-items: center;
  justify-content: space-between;
  min-height: 65px;
}

.header__text {
  text-decoration: none;
  color: white;
  font-size: 20px;
  background-color: grey;
  border-radius: 10px;
  padding: 8px;
}

.header__text:first-child {
  margin-right: 10px;
}

.header__text:hover {
  opacity: 0.6;
}
</style>