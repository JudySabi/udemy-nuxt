<template>
  <!-- 1er exo -->
  <!-- Ce Header est utilisé dans le v-container du layout default.vue -->
  <header>
    <ul>
      <li>
        <nuxt-link to="/">HOME ex1</nuxt-link>
      </li>
      <li><nuxt-link to="/users">Users</nuxt-link></li>
      <li><nuxt-link to="/products">Products</nuxt-link></li>
      <li><nuxt-link to="/dogs">Dogs</nuxt-link></li>
    </ul>
  </header>
</template>

<style scoped>
header {
  width: 100%;
  height: 60px;
  display: flex;
  justify-content: center;
  align-items: center;
}
ul {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  justify-content: space-around;
  align-items: center;
  widows: 80%;
}
li {
  margin-right: 10px;
}
</style>
