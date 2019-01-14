<template>
  <v-container>
    <v-layout 
      row
      wrap
    >
      <v-flex
        xs12
        grow
      >
        <v-text-field
          v-model="search"
          placeholder="Search"
          append-icon="search"
          single-line
        />
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  props: {
    value: {
      type: String,
      default: ''
    }
  },
  data () {
    return {
      search: this.value
    }
  },
  watch: {
    search() {
      this.$emit('input', this.search);
    }
  }
}
</script>

<style scoped>

</style>

