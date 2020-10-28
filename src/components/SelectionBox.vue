<template>
  <div class="border border-black text-center m-4 p-4 w-2/6">
    Selection : {{ selection.length }}
    <span v-if="numberSelection">joueur</span>
    <span v-else>joueurs</span>

    <ul>
      <li v-for="joueur in selection" :key="joueur.name">{{ joueur.name }}</li>
    </ul>

  </div>
  
</template>

<script>
export default {
  name: "selection-box",
  props: ['selection'],
  computed: {
    numberSelection(){
      if(this.selection.length < 2){
        return true
      }
      return false
    }
  }

}
</script>

<style>

</style>