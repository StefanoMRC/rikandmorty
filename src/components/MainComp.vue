<template>
  <div class="container mt-5">
      <div class="row">
             <AvatarComp
                v-for="(element, index) in avatars" :key="index"
                :nome='element.name'
                :origine='element.origin'
                :specie='element.species'
                :img='element.image'
                />
      </div>

  </div>
</template>

<script>
import AvatarComp from './AvatarComp.vue'
import axios from 'axios';

export default {
  name: 'MainComp',
  components:{
      AvatarComp
  },
  data() {
      return {
          avatars:[]
      }
  },
  created() {
      axios.get('https://api.sampleapis.com/rickandmorty/characters')
      .then((res)=>{
          this.avatars=res.data
      })
  },

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
