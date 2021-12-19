<template>
  <section>
    <select name="genre" id="genre" v-model="genre" @change="$emit('filterGenre' , genre)">
      <option value="all">All</option>
      <option value="rock">Rock</option>
      <option value="pop">Pop</option>
      <option value="jazz">Jazz</option>
      <option value="metal">Metal</option>
    </select>
    <!-- <select name="artist" id="artist" v-model="artist" @change="$emit('filterArtist' , artist)">
      <option :value="prop.author" v-for="(name, index) in prop" :key="index">{{prop.author}}</option>
    </select> -->
  </section>
</template>

<script>
export default {
  name: 'Select',
  data() {
    return {
      genre: 'all',
      artist: 'all',
    }
  },
  // props: {
  //   prop: Object
  // }
}
</script>

<style lang="scss" scoped>
@import '/../../assets/variables.scss';

section {
  color: $darkPrimary;
  text-align: center;
  padding: 2rem 0;

  select {
    font-family: Arial, Helvetica, sans-serif;
    font-size: 1.4rem;
    color: $darkSecondary;
    padding: .4rem .8rem;
    border-radius: 8px;
    outline: none;
  }
}
</style>