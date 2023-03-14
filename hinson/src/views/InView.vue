<script setup>
import { ref, watch } from "vue";

const todoId = ref(1);
const todoData = ref(null);

async function fetchData() {
  todoData.value = null;
  const res = await fetch(
    `https://www.balldontlie.io/api/v1/players/${todoId.value}`
  );
  todoData.value = await res.json();
}

fetchData();

watch(todoId, fetchData);
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
  <p>Player: {{ todoId }}</p>
  <button @click="todoId++">Next Player</button>
  <p v-if="!todoData">Loading...</p>
  <pre v-else>{{ todoData }}</pre>
</template>
<style></style>
