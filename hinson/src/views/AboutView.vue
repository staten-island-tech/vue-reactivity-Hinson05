<script>
// give each todo a unique id
let id = 0;

export default {
  data() {
    return {
      newTodo: "",
      todos: [],
    };
  },
  methods: {
    addTodo() {
      this.todos.push({ id: id++, text: this.newTodo });
      this.newTodo = "";
    },
    removeTodo(todo) {
      this.todos = this.todos.filter((t) => t !== todo);
    },
  },
};
</script>

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
    <form @submit.prevent="addTodo">
      <button @click="toggletwo" id="buttontwo" class="button">Purchase</button>
    </form>
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

    <h3 v-for="todo in todos" :key="todo.id">
      <h3>Title: Leaves of Grass</h3>
      <h4>Price: $12</h4>
      <img
        class="image"
        src="data:image/jpeg;base64,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"
        width="150"
        height="150"
      />
      <button @click="removeTodo(todo)">remove from cart</button>
    </h3>

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
