<template>
  <div>
    <div v-if="!loadingStatus">
      <div  class="d-flex justify-content-between align-items-center">
        <HeaderComp @funzioneRicerca="metodoSearch"/>
      </div>
      
      <GrigliaDischi
       v-for="( element, index ) in filtraggio()"
      :key="index"
      :image="element.image"
      :name="element.name"
      :species="element.species"
      :origin="element.origin"
      />
    </div>
    <div v-else>
      <LoaderComp/> 
    </div>
    <LunghezzaApi :lunghezza="filtraggio().length"/>
  </div>
</template>

<script>
import "bootstrap"
import HeaderComp from './components/HeaderComp.vue'
import GrigliaDischi from './components/GrigliaDischi.vue'
import LoaderComp from './components/LoaderComp.vue'

import axios from 'axios'

export default {
  name: 'App',
  components: {
    HeaderComp,
    GrigliaDischi,
    LoaderComp,

  },data(){
      return{
          loadingStatus: true,
          testoRicerca: ''
      }
  },
  created(){
      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then( (res) => {
            this.dischi = res.data.response
            this.loadingStatus = false
        }) 
  },
  methods: {
    metodoSearch( testo ){
      console.log(testo)
      this.testoRicerca = testo
      console.log(this.testoRicerca)
    },
    filtraggio(){
      if( this.testoRicerca === '' ){
        return this.avatarsArray
      } else{
        return this.avatarsArray.filter( (elem) => {
          return elem.name.toLowerCase().includes(this.testoRicerca.toLowerCase())
        } )
      }}
   }
}
</script>

<style lang="scss">

@import "bootstrap/dist/css/bootstrap.min.css";
@import './style/index.scss';

body {
  background-color: $bg-body;
}


</style>
