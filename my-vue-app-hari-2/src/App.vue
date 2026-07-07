<script setup>
import { computed, reactive, ref, watch } from 'vue'

const harga = ref(100000)
const diskon = ref(20)

const produk = reactive({
  nama: 'Laptop',
  harga: 10000000,
  stok: 5
})

const hargaAkhir = computed(() => {
  return harga.value - (harga.value * diskon.value / 100)
})

// reactive bs nya diganti isinya satu2 kyk begini
function gantiProduk() {
  produk.nama = 'Mouse'
  produk.harga = 200000
  produk.stok = 50

  console.log(produk)
}


watch(harga, (newValue, oldValue) => {
  console.log("Harga berubah")
  console.log("Sebelumnya :", oldValue)
  console.log("Sekarang   :", newValue)
})

watch(diskon, (newValue, oldValue) => {
  console.log("Diskon berubah")
  console.log("Sebelumnya :", oldValue)
  console.log("Sekarang   :", newValue)
})

watch(hargaAkhir, (newValue, oldValue) => {
  console.log("Harga Akhir berubah")
  console.log("Sebelumnya :", oldValue)
  console.log("Sekarang   :", newValue)
})

</script>

<template>
  <h1>Kalkulator Diskon</h1>

  <div>
    <label>Harga</label><br>
    <input type="number" v-model="harga">
  </div>

  <br>

  <div>
    <label>Diskon (%)</label><br>
    <input type="number" v-model="diskon">
  </div>

  <hr>

  <p>Harga : {{ harga }}</p>
  <p>Diskon : {{ diskon }} %</p>
  <p>Harga Akhir : {{ hargaAkhir }} </p>


  <h2>Data Produk (reactive)</h2>

  <p>Nama : {{ produk.nama }}</p>

  <button @click="gantiProduk">
    Ganti Produk
  </button>


  <p>Harga : {{ produk.harga }}</p>

  <button @click="produk.harga -= 500000">
    Diskon Harga
  </button>

  <button @click="produk.harga += 500000">
    Tambah Harga
  </button>

  <p>Stok : {{ produk.stok }}</p>

  <button @click="produk.stok++">
    Tambah Stok
  </button>

  <button @click="produk.stok--">
    Kurang Stok
  </button>

  

  </template>

  <style scoped>
  input{
    width:200px;
    padding:6px;
  }
</style>


<!-- ref - Menyimpan data reaktif

computed -Menghasilkan nilai turunan secara otomatis

watch	- Menjalankan aksi saat data berubah -->

<!-- reactive() → ubah property object (produk.nama, produk.harga, dst.). (hrs satu2)

ref() → bisa mengganti seluruh object dengan produk.value = {...}. -->

