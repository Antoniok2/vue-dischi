<template>
  <div id="navigation_bar">
    <img src="../assets/img/logo.svg" alt="">
  </div>
</template>

<script>
export default {
  name: 'Header',

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    #navigation_bar {
        width: 100%;
        height: auto;
        background-color: #2e3a46;

        img {
            width: 50px;
            margin: 20px;
            background-color: #2e3a46;
        }
    }
</style>