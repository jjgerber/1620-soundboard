<template>
  <div 
    fill-width 
    class="min-width mb-3"
  >
    <h1>{{ name }}</h1>
    <v-card 
      color="rgba(0,0,0,.5)"
      flat
      tile
      class="category"
    >
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
    name: {
      type: String,
      default: 'Sounds'
    }
  }
}
</script>

<style scoped>
.category {
  border-top: 2px rgba(255,255,255,0.7) solid !important;
  transition: 300ms;
}

.min-width {
  min-width: 250px;
}
</style>
