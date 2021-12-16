<template>
  <header>
    <img src="../../assets/logo.png" alt="spotify logo">
  </header>
</template>

<script>
export default {
  name: 'Header',
}
</script>

<style lang="scss" scoped>
@import '../../assets/variables.scss';

  header {
    height: 10vh;
    background-color: $darkPrimary;

    img {
      height: 80%;
    }
  }
</style>