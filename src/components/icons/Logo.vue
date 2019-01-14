<template>
  <img 
    :src="iconUrl"
    class="logoIcon" 
  >
</template>

<script>
export default {
  computed: {
    iconUrl() {
      return require('../../assets/logo_1620.png');
    }
  }
}
</script>

<style scoped>
.logoIcon {
  margin: 2px;
}
</style>
