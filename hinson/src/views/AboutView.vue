<script setup>
import { ref } from "vue";

const point = ref(0);
const count = ref(0);

function toggle() {
  count.value++;
  point.value += 150;
}
</script>
<script>
export default {
  data() {
    return {
      playerId: 1,
      playerData: null,
    };
  },
  methods: {
    async fetchData() {
      this.playerData = null;
      const res = await fetch(
        `https://www.balldontlie.io/api/v1/players/${this.playerId}`
      );
      this.playerData = await res.json();
    },
  },
  mounted() {
    this.fetchData();
  },
  watch: {
    playerId() {
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
    <p>Player: {{ playerId }}</p>
    <button @click="playerId++">Next Player</button>
    <p v-if="!playerData">Loading...</p>
    <pre v-else
      >{{ playerData.first_name }} {{ playerData.last_name }} ( {{
        playerData.team.full_name
      }} ) 
      Price : $150</pre
    >
    <button @click="toggle" id="button">purchase</button>
  </div>
  <div id="cart">
    <h1>Cart</h1>
    <h3></h3>
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
