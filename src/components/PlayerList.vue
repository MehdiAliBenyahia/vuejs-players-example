<template>
  <div class="border-black border m-2 p-2 flex justify-between">
    <div>
      <h1 class="text-lg font-bold">{{ playerName }}</h1>
      <p> {{ playerPositionUp }} </p>
    </div>
    <base-button
      text="Sélectionner"
      @click="addToSelection"
    >
    </base-button>
  </div>
</template>

<script>


export default {
  name: "player-list",
  props: ['player'],
  computed: {
    playerName(){
      console.log(this.player.name.split('.'))
      if(this.player.name.split('.').length > 1){
        return this.player.name.split('.')[1]
      }
      return this.player.name;
    },
    playerPositionUp(){
      return this.player.position.toUpperCase()
    }
  },
  methods: {
    addToSelection() {
      this.$emit('add-player', this.player)
    }
  }
}
</script>

<style scoped>

</style>