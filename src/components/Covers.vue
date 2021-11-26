<template>
  <div id="albums">
    <Cover v-for="album, i in Albums"
    :key="i"
    :details="album"
    />
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
    this.prendiAlbums()
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
  #albums {
    display: flex;
    flex-wrap: wrap;
    max-width: 60%;
    max-height: 720px;
    margin: 20px auto;
  }
</style>
