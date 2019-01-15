<template>
  <v-card>
    <v-card-title xs8>
      <v-layout 
        row 
        wrap
      >
        <v-flex 
          xs8 
          class="headline"
        >
          About
        </v-flex>
        <v-flex 
          xs4 
          text-xs-right
        >
          <a 
            :href="githubLink" 
            target="_blank"
            style="margin-left: auto; display: inline-block;"
          >
            <img 
              style="height: 32px; width: 32px;"
              :src="githubImage"
            >
          </a>
        </v-flex>
      </v-layout>
    </v-card-title>
    <v-card-text>
      <p>This soundboard application was written for fun by a listener of <b>1620 the Zone</b>.</p>
      <p class="mb-0">
        Click the Octocat to view the source code.
      </p>
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
  data() {
    return {
      githubImage: require('../assets/github.png'),
      githubLink: "https://github.com/jjgerber/1620-soundboard"
    }
  }
}
</script>

<style scoped>

</style>

