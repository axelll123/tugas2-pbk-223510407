<template>
  <div :class="{ 'about': true, 'about-wide': isWideScreen }">
    <h1>This is an about page</h1>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue';

const isWideScreen = ref(false);

onMounted(() => {
  // Periksa lebar layar saat komponen dimuat
  isWideScreen.value = window.innerWidth >= 1024;
});
</script>

<style>
body {
  color: rgb(252, 248, 248);
  font-family: "Dancing Script", cursive;
  margin: 0;
  background-image: url(/src/assets/3401742.jpg);
  background-size: cover;
  background-repeat: no-repeat;
}
.about {
  min-height: 100vh;
  display: flex;
  align-items: center;
}

@media (min-width: 1024px) {
  .about-wide {
    /* Tambahkan gaya tambahan jika layar lebar */
    background-color: lightblue;
  }
}
</style>
