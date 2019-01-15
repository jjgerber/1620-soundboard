<template>
  <div 
    fill-width 
    class="min-width"
  >
    <h1>{{ name }}</h1>
    <v-card class="category">
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
}

.min-width {
  min-width: 250px;
}
</style>
