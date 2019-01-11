<template>
  <v-app dark>
    <v-toolbar
      color="red darken-4"
      app
    >
      <v-toolbar-title class="headline text-uppercase">
        <div class="icon">
          <Logo />
          <div class="title">
            Soundboard
          </div>
        </div>
      </v-toolbar-title>
      <v-spacer />
      <v-btn
        flat
      >
        <span 
          class="mr-2 white--text" 
          @click="showAbout = true"
        >
          About
        </span>
      </v-btn>
    </v-toolbar>

    <v-content>
      <v-container>
        <v-layout
          text-xs-center
          wrap
        >
          <Search v-model="search" />
          <v-expand-transition mode="out-in">
            <Listing 
              v-if="!hasSearch" 
              :all-sounds="sounds"
              :search="search" 
            />
            <SearchResults 
              v-if="hasSearch"
              :sounds="sounds"
              :search="search"
            />
          </v-expand-transition>

          <v-dialog v-model="showAbout">
            <AboutDialog @dialogClosed="showAbout = false" />
          </v-dialog>
        </v-layout>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
import AboutDialog from './components/AboutDialog';
import Search from './components/Search';
import SearchResults from './components/SearchResults';
import Listing from './components/Listing';
import Logo from './components/icons/Logo';
import { sounds } from './sounds.js'

export default {
  name: 'App',
  components: {
    AboutDialog,
    Listing,
    Logo,
    Search,
    SearchResults
  },
  data () {
    return {
      search: '',
      sounds,
      showAbout: false
    }
  },
  computed: {
    hasSearch() {
      return !!this.search
    }
  }
}
</script>

<style scoped>
.title {
  display: inline-block;
  vertical-align: top;
  margin-top: 15px;
  margin-left: 5px;
}

.icon {
  margin-top: 10px;
}
</style>
