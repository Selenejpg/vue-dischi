<template>
  <header class="">
    <!--inserire contenuto componente-->
   
    <img src="../assets/img/spotify-logo.png" alt="">
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
</style>