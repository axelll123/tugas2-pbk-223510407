<template>
  <main class="main">
    <h1 :style="{ color: textColor }">{{ pageTitle }}</h1>
    <p :class="{ 'highlight': isHighlighted }">Ini adalah sebuah paragraf.</p>
    <input type="text" v-model="inputText" @input="updateText">
    <p>{{ inputText }}</p>
  </main>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const pageTitle = 'Masukkan 10 huruf, maka warna teks ini akan berubah ';
const isHighlighted = ref(false);
const inputText = ref('');
const textColor = ref('aquamarine'); // tambahkan variabel warna teks

const updateText = (event: Event) => {
  inputText.value = (event.target as HTMLInputElement).value;
  // Ganti warna teks menjadi merah jika panjang input melebihi 10 karakter
  textColor.value = inputText.value.length > 10 ? 'red' : 'aquamarine';
};
</script>

<style>
body {
  color: #fcf8f8; /* Warna teks putih */
  font-family: "Dancing Script", cursive;
  margin: 0;
  background-image: url('/src/assets/3401742.jpg'); /* Path gambar latar belakang */
  background-size: cover;
  background-repeat: no-repeat;
  height: 100vh; /* Menjamin latar belakang mengisi seluruh ketinggian layar */
  display: flex;
  justify-content: center;
  align-items: center;
}

.main {
  text-align: center;
}

h1 {
  font-size: 48px; /* Font size diperbesar */
  margin-bottom: 20px;
}

p {
  font-size: 24px; /* Font size diperbesar */
  line-height: 1.5;
}

input {
  padding: 10px;
  font-size: 16px;
  border: 2px solid #ccc;
  border-radius: 5px;
  margin-bottom: 20px;
}

.highlight {
  background-color: rgba(255, 255, 0, 0.5); /* Warna latar belakang yang lebih transparan */
}
</style>
