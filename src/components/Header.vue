<template>
  <header>
      <img src="../assets/logo.png" alt="spotify-logo">
  </header>
</template>

<script>
export default {
    name: 'Header',
}
</script>

<style scoped lang="scss">
@import '@/style/variables';
    header{
        background-color: $secondary-color;
        height: 100px;
        padding: 10px;
        img{
            height: 100%;
        }
    }
</style>