<template>
  <div class="card">
    <img :src="song.poster" :alt="song.autor + 'song' ">
    <span class="title">{{song.title}}</span>
    <span class="artist">{{song.author}}</span>
    <span class="date">{{song.year}}</span>
  </div>
</template>

<script>
export default {
  name:'Card',
  props: {
    song: Object
  }
}
</script>

<style lang="scss" scoped>
@import '../../assets/variables.scss';

  .card {
    background-color: $darkPrimary;
    margin: 1rem;
    padding: 2rem;
    border-radius: 8px;

    img {
      width: 100%;
      border-radius: 8px;
    }

    .title {
      font-size: 1.4rem;
      text-transform: uppercase;
      color: $whitePrimary;
      margin: 1.2rem 0 .3rem;
    }

    .artist,
    .date {
      color: $grey;
    }
  }
</style>