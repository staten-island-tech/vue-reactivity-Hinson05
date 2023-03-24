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
  <div class="card">
    <h2 class="text">Title: The Great Gatsby</h2>
    <h3 class="text">Price: $40</h3>
    <img
      id="image"
      src="https://media.newyorker.com/photos/5909527c019dfc3494e9defe/master/w_2560%2Cc_limit/Gatsby_1925-290.jpg"
      width="150"
      height="150"
    />
    <button v-if="awesome" @click="toggle" id="buttonone" class="button">
      purchase
    </button>
  </div>
</template>
<style>
.card {
  border: 2px solid black;
  width: 300px;
  height: 300px;
}
.text {
  text-align: center;
}
.image {
  align-items: center;
}
.button {
  align-items: center;
}
</style>
