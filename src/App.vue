<template>
  <div id="app">
    <TinyProgressBar></TinyProgressBar>
  </div>
</template>

<script>
import TinyProgressBar from './components/TinyProgressBar.vue'

export default {
  name: 'app',
  components: {
    TinyProgressBar
  }
}
</script>

<style>
html, body {
  margin: 0;
}
</style>
