<script setup>
import { RouterLink, RouterView } from "vue-router";
/*import HelloWorld from "./components/HelloWorld.vue"; */
</script>

<template>
  <header>
    <img
      id="logo"
      src="data:image/png;base64,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"
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
