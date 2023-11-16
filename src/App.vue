<script setup>
import { ref } from 'vue'

const titleClass = ref('title')
</script>

<template>
  <h1>Make me Red</h1>
</template>

<style>
.title {
  color: red;
}
.title-blue {
  color: blue;
}
</style>