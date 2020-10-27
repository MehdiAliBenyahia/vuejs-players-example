<template>
  <div>Selection : {{ selection.length }}</div>
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

export default {
  name: 'App',
  components: {
    PlayerList
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
