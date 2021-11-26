<template>
  <div id="albums">
    <Cover/>
  </div>
</template>

<script>
import Cover from '@/components/Cover.vue'

export default {
  name: 'Covers',
  components: {
    Cover
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  #albums {
    display: flex;
    flex-wrap: wrap;
    align-items: baseline;
    width: 60%;
    height: 500px;
    margin: 80px auto;

    // debug
    background-color: yellowgreen;
  }
</style>
