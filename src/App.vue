<template>
  <div id="app">
    <!-- header -->
      <Header @performSearch="searchGenre"/>
    <!-- main -->
    <main>
      <MainCards :MainCardsGenre="filteredGenre"/>
    </main>
  </div>
</template>

<script>
import axios from 'axios';
import Header from '@/components/Header.vue'
import MainCards from '@/components/MainCards.vue'

export default {
    name: 'App',
    components: {
        Header,
        MainCards,
    },
    data(){
      return{
          apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
          MainCardsList: null,
          genre: '',
      }
    },

    computed: {
        filteredGenre(){
            if(this.genre === ''){
                return this.MainCardsList;
            }

            return this.MainCardsList.filter(item => {
               return item.genre.toLowerCase().includes( this.genre.toLowerCase())
            });
        }
    },

    created(){
      this.genCard();
    },

    methods:{
      genCard() {
        axios.get(this.apiUrl)
        .then(el => {
            console.log(el.data);
            this.MainCardsList = el.data.response;
            console.log('lello',this.MainCardsList);
        })
        .catch(error => {
            console.log(error);
        })
      },
      searchGenre(text){
          this.genre = text;
      }
    }
}
</script>

<style lang="scss">
@import '~bootstrap/scss/bootstrap';
@import '@/style/variables';
@import '@/style/globals';

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
