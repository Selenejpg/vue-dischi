<template>
  <div>
    <div v-if="!loadingStatus">
      <div  class="d-flex justify-content-between align-items-center">
        <HeaderComp/>
      </div>
      
      <GrigliaDischi/>
    </div>
    <div v-else>
      <LoaderComp/> 
    </div>
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
      }
  },
  created(){
      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then( (res) => {
            this.dischi = res.data.response
            this.loadingStatus = false
        }) 
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
