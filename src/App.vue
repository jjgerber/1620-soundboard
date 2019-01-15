<template>
  <v-app dark>
    <div class="stadium-bg" />
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
        @click="showAbout = true"
      >
        <span class="mr-2 white--text">
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

          <v-fade-transition mode="out-in">
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
          </v-fade-transition>

          <v-dialog 
            v-model="showAbout"
            width="550px"
          >
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
.stadium-bg {
  z-index: -101;
  content: '';
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  display: block;
  background-image: url('./assets/bg.jpg') !important;
  background-attachment: fixed;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}
.stadium-bg:after {
  z-index: -100;
  content: '';
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  display: block;
  background-color: rgba(0, 0, 0, 0.5);
}

.title {
  display: inline-block;
  vertical-align: top;
  margin-top: 15px;
  margin-left: 5px;
}

.icon {
  margin-top: 10px;
}

.theme--dark.application {
    background: none;
}
</style>

<style>
/* Global Style Overrides! */
#app .theme--dark.v-text-field--box>.v-input__control>.v-input__slot {
    background: rgba(0,0,0,.5);
    transition: 100ms;
}

#app .theme--dark.v-text-field--box>.v-input__control>.v-input__slot:hover {
    background: rgba(0,0,0,.7);
    transition: 100ms;
}
</style>
