<template>
  <div class="card">
    <img src="https:\/\/www.onstageweb.com\/wp-content\/uploads\/2018\/09\/bon-jovi-new-jersey.jpg" alt="">
    <span class="title">new jersey</span>
    <span class="artist">Bon Jovi</span>
    <span class="date">1998</span>
  </div>
</template>

<script>
export default {
  name:'Card'
}
</script>

<style lang="scss" scoped>
@import '../../assets/variables.scss';

  .card {
    background-color: $darkPrimary;
    margin: 0 1rem;
    padding: 2rem 0;
    border-radius: 8px;

    img {
      width: 80%;
      border-radius: 8px;
    }

    .title {
      font-size: 1.5rem;
      text-transform: uppercase;
      color: $whitePrimary;
      margin: .8rem 0 .3rem;
    }

    .artist,
    .date {
      color: $grey;
    }
  }
</style>