<template>
  <div class="my-card text-center h-100 p-3 d-flex flex-column">
        <div class="card-img mb-5">
            <img :src="image" :alt="title" class="w-100">
        </div>
        <div class="card-text h-100 d-flex flex-column justify-content-center">
            <h2 class="text-white fs-3">{{ title }}</h2>
            <h3 class="text-lightgray fs-5">{{ author }}</h3>
            <h4 class="text-lightgray fs-5">{{ year }}</h4>
            <h5 class="text-white fs-5">{{ genre }}</h5>
        </div>
    </div>
</template>

<script>
export default {
    name: "CardProp",
    props:{
        image: String,
        title: String,
        author: String,
        year: String,
        genre: String
    }
}
</script>

<style scoped lang="scss">
@import '@/style/utilities';
    .my-card{
        background-color: #2e3a46;
        max-height: 800px;

        .card-text{
            padding-top: 20px;
            padding-bottom: 70px;
        }
    }

</style>