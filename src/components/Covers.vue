<template>
<div>
  <div class="loading_albums" v-if="Albums.length === 0">
    Loading
    <font-awesome-icon icon="circle-notch"></font-awesome-icon>
  </div>
  <div v-else id="albums">
    <Cover v-for="album, i in Albums"
    :key="i"
    :details="album"
    />
  </div>
</div>
  
</template>

<script>
import Cover from '@/components/Cover.vue'
import axios from 'axios'

export default {
  name: 'Covers',
  components: {
    Cover
  },
  data() {
    return {
      ApiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
      Albums: []
    }
  },
  created() {
    setTimeout(() => {
      this.prendiAlbums()
    }, 1000);
  },
  methods: {
    prendiAlbums(){
      axios
      .get(this.ApiUrl)
      .then((result) => {
        // console.log(result.data.response);
        this.Albums = result.data.response
        console.log(this.Albums);
      })
    }
  }
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

  #albums {
    display: flex;
    flex-wrap: wrap;
    max-width: 60%;
    max-height: 720px;
    margin: 20px auto;
  }
  
</style>
