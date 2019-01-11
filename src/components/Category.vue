<template>
  <div fill-width>
    <h1>{{ name }}</h1>
    <hr>
    <v-card>
      <v-container
        fluid
        grid-list-md
      >
        <v-layout
          row
          wrap
        >
          <slot />
        </v-layout>
      </v-container>
    </v-card>
  </div>
</template>

<script>
export default {
    props: {
        name: String
    }
}
</script>

<style scoped>

</style>
