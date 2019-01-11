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
        value: String
    },
    data: () => {
        this.value
    },
    methods: {
        update() {
            this.$emit('input', this.search);
        }
    }
}
</script>

<style scoped>

</style>

