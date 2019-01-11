<template>
  <v-card>
    <v-card-title class="headline">
      About
    </v-card-title>
    <v-card-text>
      About Text Will Go Here.
    </v-card-text>
    <div 
      xs6
      class="text-center pa-3 text-xs-center"
    >
      <v-btn
        color="red darken-4"
        @click="$emit('dialogClosed')"
      >
        Close
      </v-btn>
    </div>
  </v-card>
</template>

<script>
export default {

}
</script>

<style scoped>

</style>

