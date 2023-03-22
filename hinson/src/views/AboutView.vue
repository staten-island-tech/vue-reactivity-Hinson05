<script setup>
import { ref } from "vue";

const awesome = ref(true);
const count = ref(0);

function toggle() {
  count.value++;
  awesome.value = !bleh.value;
}
</script>

<!-- <script>
export default {
  data() {
    return {
      selected: "",
      destinations: [
        {
          name: "The Great Gatsby",
          price: 40,
          img: "https://cdn.onlinewebfonts.com/svg/img_208967.png",
        },
      ],
    };
  },
};
</script> -->
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
  <div class="card"></div>
  <button v-if="awesome" @click="toggle" id="button">purchase</button>
</template>
<style></style>
