<template>
  <div>
    <Bonus v-if="albums.length === 0"/>
    <div v-else id="albums">
      <Cover v-for="album, i in filterAlbumList"
      :key="i"
      :details="album"
      />
    </div>

  </div>
</template>

<script>
import Cover from '@/components/Cover.vue'
import Bonus from '@/components/Bonus.vue'
import axios from 'axios'

export default {
  name: 'Covers',
  components: {
    Cover,
    Bonus
  },
  props: {
    genreSelected: String
  },

  data() {
    return {
      apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
      albums: [],
    }
  },

  created() {
    setTimeout(() => {
      this.prendiAlbums()
    }, 1000);
  },

  computed: {
    filterAlbumList() {
      if(this.genreSelected === "all") {
        return this.albums
      }

      return this.albums.filter((item) => {
        return item.genre.includes(this.genreSelected)
        }
      )
    }
  },

  methods: {
    prendiAlbums(){
      axios
      .get(this.apiUrl)
      .then((result) => {
        // console.log(result.data.response);
        this.albums = result.data.response
        console.log(this.albums);
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
