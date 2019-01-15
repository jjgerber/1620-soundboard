<template>
  <v-container
    fluid
    xs12
    grow
  >
    <v-alert 
      v-if="!hasResults"
      color="red darken-2"
      :value="true"
      type="error"
      transition="fade-transition"
    >
      There were no results found.
    </v-alert>
    <Category
      v-else
      :name="search"
    >
      <v-flex
        v-for="(s, i) in results"
        :key="i"
        xs12
        sm6
        md4
        lg3
        xl2
      >
        <Sound
          :name="s.name"
          :audio="s.audio"
        />
      </v-flex>
    </Category>
  </v-container>
</template>

<script>
import Category from './Category';
import Sound from './Sound';

export default {
  components: {
    Category,
    Sound
  },
  props: {
    search: {
      type: String,
      default: ''
    },
    sounds: {
      type: Array,
      default: () => []
    }
  },
  data() {
    return {
      results: this.doSearch()
    }
  },
  computed: {
    hasResults() {
      return this.results.length > 0
    }
  },
  watch: {
    search() {
      this.results = this.doSearch();
    }
  },
  methods: {
    doSearch() {
      return this.sounds.filter(sound => sound.name.toLowerCase().indexOf(this.search.toLowerCase()) > -1);
    }
  }
}
</script>

<style scoped>

</style>
