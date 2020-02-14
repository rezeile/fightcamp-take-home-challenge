<template>
  <div id="app">
    <Packages />
  </div>
</template>

<script>
import Packages from './components/Packages.vue'

export default {
  name: 'App',
  components: {
    Packages
  }
}
</script>

<style>
  body {
    margin: 0px;
  }

  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }
</style>
