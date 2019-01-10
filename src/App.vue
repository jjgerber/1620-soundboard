<template>
    <v-app dark>
      <v-toolbar color="red darken-4" app>
        <v-toolbar-title class="headline text-uppercase">
          <div class="icon">
            <Logo />
            <div class="title">Sound Board</div>
          </div>
        </v-toolbar-title>
        <v-spacer></v-spacer>
        <v-btn
          flat
          href="/about"
        >
          <span class="mr-2 white--text">About</span>
        </v-btn>

      </v-toolbar>

      <v-content>
        <v-container>
          <v-layout
            text-xs-center
            wrap>
            <Search />
            <Listing />
          </v-layout>
        </v-container>
      </v-content>
    </v-app>
</template>

<script>
import Search from './components/Search';
import Listing from './components/Listing';
import Logo from './components/icons/Logo';

export default {
  name: 'App',
  components: {
    Listing,
    Logo,
    Search
  },
  data () {
    return {
      //
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
