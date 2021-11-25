<template>
  <div id="app">
    <!-- header -->
      <Header />
    <!-- main -->
    <main>
      <MainCards />
    </main>
  </div>
</template>

<script>
import Header from '@/components/Header.vue'
import MainCards from '@/components/MainCards.vue'

export default {
  name: 'App',
  components: {
    Header,
    MainCards,
  }
}
</script>

<style lang="scss">
@import '~bootstrap/scss/bootstrap';
@import '@/style/variables';

#app{
  display: flex;
  height: 100%;
  flex-direction: column;

  main{
      flex-grow: 1;
      background-color: $primary-color;
  }
}

</style>
