<template>
  <div class="selection_genre">
      <select name="" id="">
          <option value="">All</option>
          <option value="Rock">Rock</option>
          <option value="Pop">Pop</option>
          <option value="Metal">Metal</option>
          <option value="Jazz">Jazz</option>
      </select>
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
    .selection_genre {
        text-align: center;
        margin: 10px;

        select {
        padding: 5px 20px;
        border-radius: 20px;
        color: white;

        option {
            color: white;
        }
        }
    }
    
</style>