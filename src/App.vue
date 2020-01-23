<template>
  <div id="app">
    <controls />
    <grid />
    <button @click="createPdf">Download PDF</button>
  </div>
</template>

<script>
import Grid from './components/Grid.vue'
import Controls from './components/Controls.vue'
import jsPDF from 'jspdf'
import html2canvas from 'html2canvas'

export default {
  name: 'app',
  components: {
    Controls,
    Grid
  },
  methods: {
    createPdf () {
      window.html2canvas = html2canvas
      let pdfName = 'grid'
      /* eslint-disable-next-line */
      var doc = new jsPDF({
        orientation: 'landscape',
        unit: 'in',
        format: [48, 36]
      })
      doc.html(document.querySelector('svg'), {
        callback: function (doc) {
          doc.save(`${pdfName}.pdf`)
        }
      })
    }
  }
}
</script>

<style lang="scss">
#app {
  display: grid;
  grid-template-rows: auto 500px auto;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
