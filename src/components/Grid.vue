<template>
  <div>
    <svg :viewBox="`0 0 ${gridWidth * 100} ${gridHeight * 100}`">
      <defs>
        <pattern viewBox="0 0 100 100" id="grid1" width="100" height="100" patternUnits="userSpaceOnUse">
          <rect x="0" y="0" width="100" height="100" fill="transparent" stroke="grey" :stroke-width="lineWidth" :stroke-dasharray="lineWidth * 4" :stroke-dashoffset="lineWidth * 2"/>
        </pattern>
        <pattern viewBox="0 0 500 500" id="grid2" width="500" height="500" patternUnits="userSpaceOnUse">
          <rect x="0" y="0" width="500" height="500" fill="transparent" stroke="grey" :stroke-width="lineWidth" />
        </pattern>
        <pattern viewBox="0 0 1000 1000" id="grid3" width="1000" height="1000" :x="gridWidth / 2 * 100" :y="gridHeight / 2 * 100" patternUnits="userSpaceOnUse">
          <rect width="1000" height="1000" fill="url(#grid1)" />
          <rect width="1000" height="1000" fill="url(#grid2)" />
          <rect x="0" y="0" width="1000" height="1000" fill="transparent" stroke="black" :stroke-width="lineWidth * 2" :stroke-dasharray="`${lineWidth * 16} ${lineWidth * 64}`" :stroke-dashoffset="lineWidth * 8"/>

        </pattern>
      </defs>
      <rect width="100%" height="100%" fill="url(#grid3)" style="outline: solid 5mm black" />
    </svg>
  </div>
</template>

<script>
export default {
  name: 'Grid',
  props: {

  },
  data () {
    return {
      gridWidth: 36,
      gridHeight: 48,
      lineWidth: 1 / 16 * 100
    }
  }
}
</script>

<style lang="scss" scoped>
  svg {
    height: 100%;
    width: 100%;
  }
</style>
