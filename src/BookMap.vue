<script setup>
import {ref} from "vue";

const bookMap = ref(null);

async function fetchData() {
  bookMap.value = null
  const res = await fetch(
      `http://localhost:8080/vue-example`
  )
  bookMap.value = await res.json();
}
fetchData();

</script>
<template>
  <div>{{bookMap}}</div>

  <ul>
    <li>{{bookMap.classic}}</li>
    <li>{{bookMap.fiction}}</li>
  </ul>
</template>