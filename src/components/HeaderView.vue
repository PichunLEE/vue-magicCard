<template>
  <div id="header-wrapper">
    <div class="container">
      <!-- Header -->
      <header id="header">
        <div class="inner">
          <!-- Logo -->
          <h1><router-link to="/">Magic</router-link></h1>

          <!-- Nav -->
          <nav id="nav">
            <router-link to="/">Home</router-link>
            <router-link :to="{ name: 'CollectionView' }"
              >Ma Collection
            </router-link>
          </nav>
        </div>
      </header>

      <!-- Banner -->
      <div id="banner">
        <h2><strong>Magic Card:</strong> Ma collection</h2>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HeaderView",
};
</script>

<style>
#nav a {
  font-size: 20px;
  color: aliceblue;
  margin-left: 15px;
  text-decoration: none;
}
</style>
