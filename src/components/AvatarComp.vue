<template>
  <div class="col-3 text-center py-4">
    <img :src="img" alt="" class="rounded-circle">
    <h2>{{nome}}</h2>
    <span>{{origine}}</span>
    <h4>{{specie}}</h4>
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
