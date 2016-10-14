<template>
  <main id="app">
    <h1>Latest Posts</h1>
    <Posts></Posts>
  </main>
</template>

<script>
import Posts from './components/Posts.vue';

export default {
  components: {
    Posts
  }
}
</script>

<style>
body {
  font-family: -apple-system, BlinkMacSystemFont,
    "Segoe UI", "Roboto", "Oxygen", "Ubuntu", "Cantarell",
    "Fira Sans", "Droid Sans", "Helvetica Neue",
    sans-serif;
}
</style>
