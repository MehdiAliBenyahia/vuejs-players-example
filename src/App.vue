<template>
  <selection-box
    :selection="selection"
  >
  </selection-box>
  <player-list 
    v-for="(player, index) in team.players"
    :key="index"
    :player="player"
    @add-player="addPlayerToSelection"
    >
    </player-list>
</template>

<script>
import teamData from './data/players.json'
import PlayerList from './components/PlayerList.vue'
import SelectionBox from './components/SelectionBox.vue'
export default {
  name: 'App',
  components: {
    PlayerList,
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
