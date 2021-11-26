<template>
  <div class="my-container">
      <div class="container-fluid d-flex justify-content-center align-items-center h-100">
        <ul v-if="MainCardsGenre !== null" class="d-flex flex-wrap list-unstyled justify-content-center w-100">
            <li v-for="(card, index) in MainCardsGenre" :key="`${index}`" class="px-4 mb-4">

                <CardProp :image="card.poster" :title="card.title" :author="card.author" :year="card.year" :genre="card.genre"/>

            </li>
        </ul>
        <Loader v-else title="ALBUM LIST"/>
      </div>
  </div>
</template>

<script>
// import axios from 'axios';
import CardProp from '@/components/CardProp.vue'
import Loader from '@/components/Loader.vue'
export default {
    name: 'MainCards',
    components:{
        CardProp,
        Loader,
    },
    props:{
        MainCardsGenre: Array,
    }
}
</script>

<style scoped lang="scss">
@import '@/style/variables';
@import '@/style/utilities';
    .my-container{
        width: 85%;
        height: 100%;
        margin: 0 auto;
        padding-top: 70px;

        li{
            width: calc(100% / 8);
        }
    }
</style>