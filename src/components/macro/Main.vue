<template>
  <main>
    <div class="card-container">
      <Card class="card"/>
      <Card class="card"/>
      <Card class="card"/>
      <Card class="card"/>
    </div>
  </main>
</template>

<script>
import Card from './../commons/Card.vue';

export default {
  name: 'Main',
  components: {
    Card
  }
}
</script>

<style lang="scss" scoped>
@import '../../assets/variables.scss';

main {
  height: 90vh;
  background-color: $darkSecondary ;

  .card-container {
    width: 70%;
    display: grid;
    grid-template-columns: 25% 25% 25% 25%;
    margin: 0 auto;
    padding: 4rem 0;

    
    .card {
      display: flex;
      flex-direction: column;
      align-items: center;

    }
  }
}
</style>