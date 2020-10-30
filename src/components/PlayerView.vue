<template>

  <img alt="Vue logo" src="../assets/img/logo.png">
  <div class="flex">
    <div class="w-1/5">
      <selection-box
        :selection="selection"
      >
      </selection-box>
    </div>
    

    <div class="w-4/5 mt-2">
      <player-card 
        v-for="(player, index) in team.players"
        :key="index"
        :player="player"
        @add-player="addPlayerToSelection"
        >
      </player-card>
    </div>
    

  </div>
    
</template>

<script>
import teamData from '../data/players.json'
import PlayerCard from './PlayerCard.vue'
import SelectionBox from './SelectionBox.vue'

export default {
  name: "player-view",
  components: {
    PlayerCard,
    SelectionBox
  },
  data() {
    return {
      team: teamData,
      selection: []
    }
  },
  methods: {
    addPlayerToSelection(player){
      this.selection.push(player)
      this.$emit('child-event', player)
    }
  }
}
</script>

<style scoped>

</style>