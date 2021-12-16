<template>
  <main>
    <div class="card-container">
      <Card class="card" v-for="(song, index) in songs" :key="index" :song="song"/>
    </div>
  </main>
</template>

<script>
import Card from './../commons/Card.vue';
import axios from '../../../node_modules/axios';

export default {
  name: 'Main',
  components: {
    Card
  },
  data() {
    return {
      songs: null,
    }
  },
  created() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
    .then((response) => {
      // handle success
      this.songs = response.data.response
    })
    .catch(function (error) {
      // handle error
      console.log(error);
    })
  }
}
</script>

<style lang="scss" scoped>
@import '../../assets/variables.scss';

main {
  height: 90vh;
  background-color: $darkSecondary;
  overflow-y: scroll;

  .card-container {
    width: 70%;
    display: grid;
    grid-template-columns: 25% 25% 25% 25%;
    margin: 0 auto;
    padding: 2rem 0;

    
    .card {
      display: flex;
      flex-direction: column;
      align-items: center;
      text-align: center;
      transition: filter .5s;
      filter: brightness(.9);

      &:hover {
        cursor: pointer;
        filter: brightness(1.1);
      }
    }
  }
}
</style>