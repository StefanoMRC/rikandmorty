<template>
  <div>
    <form class="d-flex">
        <input type="text" class="form-control me-3" v-model="ricerca">
        <button 
        type="submit" 
        class="btn btn-primary"
        @click.prevent="$emit('funzRicerca', ricerca)"
        >Ricerca</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'RicercaComp',
    data() {
        return {
            ricerca:''
        }
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
