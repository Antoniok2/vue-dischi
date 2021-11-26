<template>
  <div id="album">
    
  </div>
</template>

<script>
export default {
  name: 'Cover'
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  #album {
    width: calc((100% / 5) - 20px);
    height: 230px;
    margin: 10px;
    background-color: #2e3a46;

    // debug
    border: solid 1px yellow;
  }
</style>