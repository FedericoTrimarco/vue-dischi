<template>
  <header class="d-flex justify-content-between align-items-center">
      <img src="../assets/logo.png" alt="spotify-logo">
      
      <select v-model="genre" class="text-white">
          <option value="">Genere Musicale</option>
          <option value="Rock">Rock</option>
          <option value="Pop">Pop</option>
          <option value="Jazz">Jazz</option>
          <option value="Metal">Metal</option>
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