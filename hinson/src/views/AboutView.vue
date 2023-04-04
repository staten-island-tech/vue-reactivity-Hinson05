<script setup>
import { ref } from "vue";

const point = ref(0);
const count = ref(0);
const cart = ref([]);

function toggle() {
  count.value++;
  point.value += 150;
  cart.push();
}
</script>
<script>
export default {
  data() {
    return {
      todoId: 1,
      todoData: null,
    };
  },
  methods: {
    async fetchData() {
      this.todoData = null;
      const res = await fetch(
        `https://www.balldontlie.io/api/v1/players/${this.todoId}`
      );
      this.todoData = await res.json();
    },
  },
  mounted() {
    this.fetchData();
  },
  watch: {
    todoId() {
      this.fetchData();
    },
  },
};
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
      {{ count }}
    </h2>
    <h3>Cost: ${{ point }}</h3>
  </div>
  <div id="idk">
    <p>Player: {{ todoId }}</p>
    <button @click="todoId++">Next Player</button>
    <p v-if="!todoData">Loading...</p>
    <pre v-else
      >{{ todoData.first_name }} {{ todoData.last_name }} ( {{
        todoData.team.full_name
      }} ) 
      Price : $150</pre
    >
    <button @click="toggle" id="button">purchase</button>
  </div>
  <div id="cart">
    <h1>Cart</h1>
    <li>
      {{ todoData.first_name }} {{ todoData.last_name }} (
      {{ todoData.team.full_name }} ) Price : $150
    </li>
  </div>
</template>
<style>
#button {
  width: 400px;
  height: 100px;
}
#idk {
  border: solid 5px black;
  width: 500px;
  height: 500px;
}
</style>
