<template>
  <div>
    <Selects @search="selectGenre" />
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
import Selects from '@/components/Selects.vue'
import axios from 'axios'

export default {
  name: 'Covers',
  components: {
    Cover,
    Bonus,
    Selects
  },

  data() {
    return {
      apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
      albums: [],
      optionGenre: "all"
    }
  },

  created() {
    setTimeout(() => {
      this.prendiAlbums()
    }, 1000);
  },

  computed: {
    filterAlbumList() {
      if(this.optionGenre === "all") {
        return this.albums
      }

      return this.albums.filter((item) => {
        return item.genre.includes(this.optionGenre)
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
    },

    selectGenre(genere) {
      this.optionGenre = genere;
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
