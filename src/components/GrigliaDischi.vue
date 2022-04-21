<template>
  <header class="row mx-5">
      <div class="container padding">
        <div class="row row-cols-5 text-white my-4 text-center">
            <div class="mt-5" v-for="(element, index) in dischi" :key="index">
                <div class="bg-card height p-3">
                    <img  class="img-fluid mt-5" :src="element.poster" alt="">
                    <h3 class="mt-4 fs-6">{{element.title}}</h3>
                    <h4 class="font gray">{{element.author}}</h4>
                    <h4 class="font gray">{{element.year}}</h4>
                </div>
                
            </div>
        </div> 
      </div>
    
  </header>
</template>

<script>
import axios from 'axios'

export default {
  //Cambiare il nome con quello del componente creato
  name: 'HeaderComp',
  data(){
      return{
          dischi: []
      }
  },
  created(){
      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then( (res) => {
            this.dischi = res.data.response
        }) 
  }
}
</script>

<style scoped lang="scss">
 /*Inserire style componente*/
  @import '../style/index.scss';

 .padding{
    padding: 40px;
 }

 .font{
     font-size: 15px;
 }

 .bg-card {
     background-color: $header-bg;
 }
.height{
    height: 100%;
}
 .gray{
    color: gray;
 }
</style>