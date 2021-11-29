<template>
  <div class="loading_albums">
    Loading
    <font-awesome-icon icon="circle-notch"></font-awesome-icon>
  </div>
</template>

<script>
export default {
  name: 'Bonus'

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
 .loading_albums {
    border: solid 2px black;
    background-color: #2e3a46;
    color: white;
    padding: 10px 20px;
    text-align: center;
    font-size: 30px;
  }
</style>