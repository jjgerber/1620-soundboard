<template>
  <v-container
    fluid
    xs12
    grow
  >
    <Category 
      v-for="(category, i) in categories" 
      :key="i" 
      :name="category"
    >
      <v-flex
        v-for="(s, i2) in categorySounds(category)"
        :key="i2"
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
  import Category from '../components/Category';
  import Sound from '../components/Sound';
  import { sounds } from '../sounds.js'

  export default {
    components: {
      Category,
      Sound
    },
    data: () => ({
      sounds
    }),
    computed: {
      categories() {
        return [...new Set(this.sounds.map(item => item.category))] || ['NA'];
      }
    },
    methods: {
      categorySounds(category) {
        return this.sounds.filter(sound => sound.category === category);
      }
    }
  }
</script>
