<template>
  <header class="d-flex justify-content-between align-items-center">
      <img src="../assets/logo.png" alt="spotify-logo">

      <select v-model="genre" class="text-white" @change="$emit('performSearch', genre)">
          <option value="">Tutti i generi</option>

          <option v-for="(card, index) in cardsArray" :key="`${index}`" :value="card" >{{ card }}</option>
          
      </select>
  </header>
</template>

<script>
export default {
    name: 'Header',
    data(){
        return{
            genre: '',
        }
    },
    props: {
        cardsArray: Array,
    }
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

        select{
            width: 200px;
            height: 50%;
            background-color: $primary-color;
            border-radius: 10px;
        }
    }
</style>