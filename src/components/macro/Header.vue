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
    display: flex;
    align-items: center;
    height: 10vh;
    background-color: $darkPrimary;

    img {
      height: 70%;
      margin-left: 1rem;
    }
  }
</style>