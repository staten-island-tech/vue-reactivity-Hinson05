<script setup>
import { ref } from "vue";

DOMSelectors
const point = ref(0);
const count = ref(0);

function toggle() {
  count.value += 40;
  point.value++;
  console.log("The Great Gatsby");
}
function toggletwo() {
  count.value += 12;
  point.value++;
  console.log("Leaves of Grass");
  DOMSelectors.cart.insertAdjacentHTML(
    "afterend",
    `<p id="results">Leaves of Grass</p>`
  );
}
function togglethree() {
  count.value += 13;
  point.value++;
  console.log("The Crucible");
}
function togglefour() {
  count.value += 9;
  point.value++;
  console.log("Lolita");
}
</script>

<template>
  <div class="shop">
    <h2>
      <img
        id="icon"
        src="https://cdn.onlinewebfonts.com/svg/img_208967.png"
        width="35"
        height="35"
      />
      {{ point }}
    </h2>
    <h3>Price: ${{ count }}</h3>
  </div>

  <div class="card" id="cardone">
    <h2 class="text">Title: The Great Gatsby</h2>
    <h3 class="text">Price: $40</h3>
    <img
      class="image"
      src="https://media.newyorker.com/photos/5909527c019dfc3494e9defe/master/w_2560%2Cc_limit/Gatsby_1925-290.jpg"
      width="150"
      height="150"
    />
    <div></div>
    <button @click="toggle" id="buttonone" class="button">purchase</button>
  </div>

  <div class="card" id="cardtwo">
    <h2 class="text">Title: Leaves of Grass</h2>
    <h3 class="text">Price: $12</h3>
    <img
      class="image"
      src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/3f/Leavesofgrass_margaretcook.webp/220px-Leavesofgrass_margaretcook.webp.png"
      width="150"
      height="150"
    />
    <div></div>
    <button @click="toggletwo" id="buttontwo" class="button">purchase</button>
  </div>

  <div class="card" id="cardthree">
    <h2 class="text">Title: The Crucible</h2>
    <h3 class="text">Price: $13</h3>
    <img
      class="image"
      src="https://upload.wikimedia.org/wikipedia/en/thumb/7/75/Cruciblecover.jpg/220px-Cruciblecover.jpg"
      width="150"
      height="150"
    />
    <div></div>
    <button @click="togglethree" id="buttontwo" class="button">purchase</button>
  </div>

  <div class="card" id="cardfour">
    <h2 class="text">Title: Lolita</h2>
    <h3 class="text">Price: $9</h3>
    <img
      class="image"
      src="data:image/jpeg;base64,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"
      width="150"
      height="150"
    />
    <div></div>
    <button @click="togglefour" id="buttontwo" class="button">purchase</button>
  </div>
  <div id="cart">
    <h1>Cart</h1>
    <h3></h3>
  </div>
</template>
<style>
.card {
  border: 2px solid black;
  width: 300px;
  height: 300px;
  padding: 5px;
  margin: 5px;
}
.text {
  text-align: center;
}
.image {
  align-items: center;
  text-align: center;
}
.button {
  align-items: center;
  text-align: center;
}
</style>
