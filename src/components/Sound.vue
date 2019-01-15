<template>
  <v-card
    :ripple="true"
    :raised="true"
    color="grey" 
    :light="true" 
    width="100%" 
    :min-height="65" 
    :min-width="200"
    class="pa-2 center-middle sound-button"
    @click="playSound()"
  >
    {{ name }}
  </v-card>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      default: 'Sound'
    },
    audio: {
      type: String,
      default: null
    }
  },
  methods: {
    playSound() {
      new Audio(this.audio).play();
    }
  }
}
</script>

<style scoped>
.center-middle {
    display: flex;
    align-items: center;
    justify-content: center;
}

.sound-button {
  cursor: pointer;
}
</style>
