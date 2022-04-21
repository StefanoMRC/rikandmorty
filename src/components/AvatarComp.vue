<template>
  <div class="col-3 text-center p-5">
    <img :src="img" alt="" class="rounded-circle img-fluid">
    <h3 class="mt-2">{{nome}}</h3>
    <div class="border border-1 w-25 m-auto border-dark"></div>
    <p class="mb-0 mt-1">{{origine}}</p>
    <h5>{{specie}}</h5>
  </div>
</template>

<script>
export default {
  name: 'AvatarComp',
  props:{
      nome:String,
      img:String,
      specie:String,
      origine:String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
