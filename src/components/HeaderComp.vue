<template>
  <header class="d-flex justify-content-between align-items-center">
    <!--inserire contenuto componente-->
   
    <img src="../assets/img/spotify-logo.png" alt="">
    <select v-model.trim="selectText" class="form-select width" aria-label="Default select example">
      <option @click.prevent="$emit( 'funzioneRicerca, selectText' )" value="1">Pop</option>
      <option value="2">Rock</option>
      <option value="3">Metal</option>
      <option value="4">Jazz</option>
    </select>

  </header>
</template>

<script>
export default {
  //Cambiare il nome con quello del componente creato
  name: 'HeaderComp',
  data() {
    return {
      selectText: ' ',
      testoRicerca: ''
    }
}
}
</script>

<style scoped lang="scss">
 /*Inserire style componente*/
 @import '../style/index.scss';

 header {
    background-color: $header-bg;
    padding: 20px;
    width: 100vw;
 }

 img{
    width: 80px;
 }

 .width{
   width: 10%;
 }
</style>