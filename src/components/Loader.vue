<template>
    <div class="loader text-center text-light">
        <h1>{{ title }}</h1>
        <i class="load-icon fas fa-circle-notch my-5"></i>
    </div>
</template>

<script>
export default {
    name: 'Loader',
    props: {
        title: String,
    },
}
</script>

<style scoped lang="scss">
    h1{
        font-size: 50px;
    }
    .load-icon{
        font-size: 80px;
        animation: rotation 1.2s linear infinite;
        
        @keyframes rotation {
            0%{
                transform: rotate(-360deg);
            }
        }
    }
</style>