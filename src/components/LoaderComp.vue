<template>
  <header class="d-flex align-items-center justify-content-center">
    <div class="color d-flex justify-content-center">
      <h2>Loading</h2>
      <img class="icon" src="../assets/img/circle-notch-solid.svg" alt="">
    </div>
    
  </header>
</template>

<script>
export default {
  //Cambiare il nome con quello del componente creato
  name: 'LoaderComp',
}
</script>

<style scoped lang="scss">
 /*Inserire style componente*/
 .icon {
  margin-left: 20px;
  animation-name: spin;
  animation-duration: 1500ms;
  animation-iteration-count: infinite;
  animation-timing-function: linear; 
  width: 14%;
}

@keyframes spin {
    from {
        transform:rotate(0deg);
    }
    to {
        transform:rotate(360deg);
    }
}

.color{
  background-color: #374350;
  color: rgb(112, 252, 112);
  width: 15vw;
  padding: 6px;
}

header{
  height: 100vh;
}
</style>