<script setup>
import { RouterLink, RouterView } from "vue-router";
/*import HelloWorld from "./components/HelloWorld.vue"; */
</script>

<template>
  <header>
    <img
      id="logo"
      src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRK30LkGqZEASURehCGGm4zhq0K6whNTDMTjQ&usqp=CAU"
      width="250"
      height="150"
    />

    <div class="wrapper">
      <HelloWorld msg=" " />
      <h1>Book Store</h1>

      <nav>
        <RouterLink to="/about">Shop</RouterLink>
        <RouterLink to="/">Cart</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
  #logo {
    padding-bottom: 15px;
  }
}
</style>
