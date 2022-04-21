<template>
  <header class="d-flex justify-content-between align-items-center">
    <!--inserire contenuto componente-->
   
    <img src="../assets/img/spotify-logo.png" alt="">
    <select class="form-select width" aria-label="Default select example">
      <option value="1">Pop</option>
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
}
</script>

<style scoped lang="scss">
 /*Inserire style componente*/
 @import '../style/index.scss';

 header {
    background-color: $header-bg;
    padding: 20px;
 }

 img{
    width: 80px;
 }

 .width{
   width: 13%;
 }
</style>