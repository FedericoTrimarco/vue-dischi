<template>
  <div class="my-container">
      <div class="container-fluid">
        <ul class="d-flex flex-wrap list-unstyled justify-content-center">
            <li v-for="(card, index) in MainCardsList" :key="`${index}`" class="col-lg-2 col-md-4 col-sm-6  col-12 px-4 mb-4">

                <CardProp :image="card.poster" :title="card.title" :author="card.author" :year="card.year" :genre="card.genre"/>

            </li>
        </ul>

      </div>
  </div>
</template>

<script>
import axios from 'axios';
import CardProp from '@/components/CardProp.vue'
export default {
    name: 'MainCards',
    components:{
        CardProp,
    },
    data(){
        return{
            apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
            MainCardsList: [],
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
        }
    }
}
</script>

<style scoped lang="scss">
@import '@/style/variables';
@import '@/style/utilities';
    .my-container{
        width: 85%;
        margin: 0 auto;
        padding-top: 70px;
    }
    /* li{
        height: 500px;
    } */
</style>