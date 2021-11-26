<template>
  <div id="app">
    <Covers/>
  </div>
</template>

<script>
import Covers from './components/Covers.vue'

export default {
  name: 'App',
  components: {
    Covers
  }
}
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  background-color: #1e2d3b;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

</style>
