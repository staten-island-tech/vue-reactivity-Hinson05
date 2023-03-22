<script setup>
import { RouterLink, RouterView } from "vue-router";
/*import HelloWorld from "./components/HelloWorld.vue"; */
</script>

<template>
  <header>
    <img
      id="logo"
      src="https://th.bing.com/th/id/OIP.h1t-m8AH-9KSwHCslzXvagHaFj?w=240&h=180&c=7&r=0&o=5&pid=1.7"
      width="250"
      height="150"
    />

    <div class="wrapper">
      <HelloWorld msg="Book Store" />
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
