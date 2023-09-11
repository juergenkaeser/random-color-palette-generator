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
    data() {
      return {
        url: "http://colormind.io/api/",
        data: {
          model : "default"
        },
        palette: []
      }
    },
    methods: {
      generatePalette: function () {
        var http = new XMLHttpRequest()

        http.onreadystatechange = function() {
          if(http.readyState == 4 && http.status == 200) {
            var palette = JSON.parse(http.responseText).result
            console.log(palette)
            // TODO: Use palette to show PaletteItems inside of PaletteList
          }
        }

        http.open("POST", this.url, true)
        http.send(JSON.stringify(this.data))
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
