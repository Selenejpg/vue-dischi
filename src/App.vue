<template>
  <div>
    <HeaderComp/>
    <GrigliaDischi/>
  </div>
</template>

<script>
import "bootstrap"
import HeaderComp from './components/HeaderComp.vue'
import GrigliaDischi from './components/GrigliaDischi.vue'

export default {
  name: 'App',
  components: {
    HeaderComp,
    GrigliaDischi
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
