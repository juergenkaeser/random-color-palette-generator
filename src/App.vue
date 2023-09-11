<template>
  <div class="content-wrapper">
    <h1>Color Palette Generator</h1>
    <palette-list></palette-list>
    <button @click="generatePalette">Generate Palette</button>
  </div>
</template>

<script lang="ts">
  import PaletteList from './components/PaletteList.vue'

  export default {
    components: {
      PaletteList
    },
    methods: {
      generatePalette: () => {
        console.log("generatePalette called!");
      }
    }
  }
</script>

<style lang="scss" scoped>
  .content-wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100vw;
    height: 100vh;
    background-color: lightgray;
  }
</style>
