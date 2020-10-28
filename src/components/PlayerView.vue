<template>
  <selection-box
    :selection="selection"
  >
  </selection-box>

  <player-card 
    v-for="(player, index) in team.players"
    :key="index"
    :player="player"
    @add-player="addPlayerToSelection"
    >
  </player-card>
    
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
    }
  }
}
</script>

<style>

</style>