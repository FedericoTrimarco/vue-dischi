<template>
  <div id="spotify">
    <!-- header -->
      <Header />
    <!-- main -->

  </div>
</template>

<script>
import Header from '@/components/Header.vue'

export default {
  name: 'App',
  components: {
    Header,
  }
}
</script>

<style lang="scss">
@import '~bootstrap/scss/bootstrap';
@import '@/style/variables';

#spotify{
  background-color: $primary-color;
  height: 100vh;
}

</style>
