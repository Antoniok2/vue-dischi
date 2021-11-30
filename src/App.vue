<template>
  <div id="app">
    <header>
      <Header/>
    </header>

    <main>
      <Selects @search="selectGenre" />
      <Covers :genreSelected="optionGenre"/>
    </main>
    
  </div>
</template>

<script>
import Covers from './components/Covers.vue'
import Header from './components/Header.vue'
import Selects from './components/Selects.vue'

export default {
  name: 'App',
  components: {
    Header,
    Covers,
    Selects
  },
  data() {
    return {
      optionGenre: "all"
    }
  },
  methods: {
    selectGenre(genere) {
      this.optionGenre = genere;
      console.log(this.optionGenre);
    }
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
  width: 100vw;
  height: 100vh;
}

</style>
