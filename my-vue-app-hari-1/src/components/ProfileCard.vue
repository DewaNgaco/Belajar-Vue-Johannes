<script setup>
const name = "ME"
const job = "Programmer"
const city = "Jakarta"
const age = 51
</script>

<template>
  <div>
    <h2>{{ name }}</h2>
    <p>{{ job }}</p>
    <p>{{ city }}</p>
    <p>{{ age }}</p>
  </div>
</template>

<style scoped>
div{
  border:1px solid gray;
  padding:15px;
  width:220px;
}
</style>