<template>
  <div class="container mt-5">
        <RicercaComp @funzRicerca='metodoRicerca'/>
      <div class="row justify-content-between" v-if="!loadingStatus">
        
          
             <AvatarComp
                v-for="(element, index) in filtraggio" :key="index"
                :nome='element.name'
                :origine='element.origin'
                :specie='element.species'
                :img='element.image'
                />
      </div>
      <div v-else>
          <LoaderComp/>
      </div>
  </div>
</template>

<script>
import AvatarComp from './AvatarComp.vue'
import LoaderComp from './LoaderComp.vue'
import RicercaComp from './RicercaComp.vue'
import axios from 'axios';

export default {
  name: 'MainComp',
  components:{
      AvatarComp,
      LoaderComp,
      RicercaComp
  },
  data() {
      return {
          avatars:[],
          loadingStatus:true,
          testoRicerca:''
      }
  },
  computed:{
      filtraggio(){
          if (this.testoRicerca=='') {
              return this.avatars
          }
          return this.avatars.filter((element)=> {
              return element.name
                    .toLowerCase()
                    .includes(this.testoRicerca.toLowerCase())
          })
      }
  },
  created() {
      axios.get('https://api.sampleapis.com/rickandmorty/characters')
      .then((res)=>{
          this.avatars=res.data
          this.loadingStatus=false
          
      })
  },
  methods: {
      metodoRicerca(testo){
          this.testoRicerca=testo;
      }
  },

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
