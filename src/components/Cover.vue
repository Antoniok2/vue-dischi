<template>
  <div id="album">
    <div class="style_album">
        <img :src="details.poster" :alt="details.title">
    </div>
    <h3>{{details.title}}</h3>
    <div>{{details.author}}</div>
    <span>{{details.year}}</span>
  </div>
</template>

<script>
export default {
  name: 'Cover',
  props: {
      details: Object
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  #album {
    width: calc((100% / 5) - 20px);
    height: 280px;
    margin: 10px;
    background-color: #2e3a46;;
    text-align: center;
    cursor: pointer;

    .style_album {
        margin: 10px;
        background-color: #2e3a46;

        img {
            width: 80%;
        }
    }

    h3 {
        color: white;
        margin-bottom: 5px;
        background-color: #2e3a46;
    }

    div {
        color: #6e6f6a;
        background-color: #2e3a46;
    }

    span {
        color: #6e6f6a;
        background-color: #2e3a46;
    }

    &:hover {
        transform: scale(1.1);
    }
  }
</style>