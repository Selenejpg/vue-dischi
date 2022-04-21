<template>
  <div>
    <div v-if="!loadingStatus">
      <HeaderComp/>
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

export default {
  name: 'App',
  components: {
    HeaderComp,
    GrigliaDischi,
    LoaderComp
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
