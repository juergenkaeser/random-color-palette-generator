<template>
  <div class="list-wrapper">
    <palette-item></palette-item>
  </div>
</template>

<script lang="ts">
  import PaletteItem from './PaletteItem.vue'

  export default {
    components: {
      PaletteItem
    }
  }
</script>

<style scoped>
  .list-wrapper {
    margin-bottom: 40px;
  }
</style>
