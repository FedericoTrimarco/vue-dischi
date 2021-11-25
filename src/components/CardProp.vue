<template>
  <div class="my-card text-center h-100 p-3 d-flex flex-column">
        <div class="card-img mb-5">
            <img :src="image" :alt="title" class="w-100">
        </div>
        <div class="card-text">
            <h2 class="text-white">{{ title }}</h2>
            <h3 class="text-lightgray">{{ author }}</h3>
            <h4 class="text-lightgray">{{ year }}</h4>
            <h5 class="text-white">{{ genre }}</h5>
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

    .my-card{
        background-color: #2e3a46;
        max-height: 800px;

        .card-img{
            height: 50%;
        }
        .card-text{
            padding-top: 20px;
            height: 50%;
        }
    }

</style>