<script setup>
import { ref, computed } from 'vue'
import Home from './Home.vue'
import SomeOtherPage from './SomeOtherPage.vue'
import BookList from "./BookMap.vue";

const routes = {
  '/': Home,
  '/some-other-page': SomeOtherPage,
  '/book-list': BookList
}

const currentPath = ref(window.location.hash)
window.addEventListener('hashchange', () => {
  currentPath.value = window.location.hash
})

const currentView = computed(() => {
  return routes[currentPath.value.slice(1) || '/']
})

</script>

<template>
  <ul>
    <li> <a href= "#/"> home page </a> </li>
    <li> <a href="#/some-other-page">SomeOtherPage</a> </li>
    <li> <a href="#/book-list">BookList</a> </li>
  </ul>
  <component :is="currentView" />
</template>