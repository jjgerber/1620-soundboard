<template>
  <v-container
    fluid
    xs12
    grow
    pt-0
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

  export default {
    components: {
      Category,
      Sound
    },
    props: {
      allSounds: {
        type: Array,
        default: () => []
      }
    },
    computed: {
      categories() {
        return [...new Set(this.allSounds.map(item => item.category))] || ['NA'];
      }
    },
    methods: {
      categorySounds(category) {
        return this.allSounds.filter(sound => sound.category === category);
      }
    }
  }
</script>
