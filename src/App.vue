<template>
  <div id="app">
    <!-- header -->
      <Header @performSearch="searchGenre" :cardsArray="listGenr"/>
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

export default{
  name: 'App',
  components: {
    Header,
    MainCards,
  },

  data() {
    return {
      apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
      MainCardsList: null,
      listGenr: [],
      genre: '',
    }
  },

  computed: {
    filteredGenre(){
      if(this.genre === ''){
        return this.MainCardsList;
      }

      return this.MainCardsList.filter(item => {
        return item.genre.includes( this.genre)
      });
    },
    
  },

  created() {
    this.genCard();
  },

  methods:{
    genCard() {
      axios.get(this.apiUrl)
      .then(el => {

        this.MainCardsList = el.data.response;
        this.filteredChoisGenre()

      })
        .catch(error => {
          console.log(error);
        })
    },
    searchGenre(text) {
      this.genre = text;
    },
    filteredChoisGenre(){
         this.MainCardsList.forEach(el => {
           if(!this.listGenr.includes(el.genre)){
              this.listGenr.push(el.genre)
           }
         });
           
    },

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
