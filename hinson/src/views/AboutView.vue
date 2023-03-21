<script setup>
import { ref } from "vue";

const awesome = ref(true);
const count = ref(0);

function toggle() {
  count.value++;
  awesome.value = !bleh.value;
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
  </div>
  <div>
    <p>Player: {{ todoId }}</p>
    <button @click="todoId++">Next Player</button>
    <p v-if="!todoData">Loading...</p>
    <pre v-else
      >{{ todoData.first_name }} {{ todoData.last_name }} ( {{
        todoData.team.full_name
      }} )</pre
    >
  </div>
  <button v-if="awesome" @click="toggle" id="button">purchase</button>
</template>
<style></style>
