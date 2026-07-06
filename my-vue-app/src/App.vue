<script setup>
import { ref } from 'vue';
import ProfileCard from './components/ProfileCard.vue'

const count = ref(0)

function tambah() {
  count.value++
}

function kurang() {
  count.value--
}

</script>

<template>
  <ProfileCard />

   <h2>{{ count }}</h2>

  <button @click="tambah">
    Tambah
  </button>

  <button @click="kurang">
    Kurang
  </button>

  <!-- Vue menggunakan reactivity sehingga perubahan data otomatis memperbarui tampilan. -->

</template>

