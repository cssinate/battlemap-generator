<template>
    <div>
        <fieldset>
            <legend>Page Size</legend>
            <section>
                <input type="radio" name="pageSize" id="pageSize-preset" value="preset">
                <label for="pageSize-preset">Preset</label>
                <select :disabled="pageSizePreset != 'preset'">
                    <option value="8p5x11">Letter</option>
                    <option value="a4">A4</option>
                    <option value="18x24">Small Poster</option>
                    <option value="24x36">Medium Poster</option>
                    <option value="36x48">Large Poster</option>
                </select>
            </section>
            <section>
                <input type="radio" name="pageSize" id="pageSize-custom" value="custom">
                <label for="pageSize-custom">Custom</label>
                <input type="number" :disabled="pageSizePreset != 'custom'">
                <input type="number" :disabled="pageSizePreset != 'custom'">
            </section>
        </fieldset>
        <fieldset>
            <legend>Grid 1</legend>
            <input type="color" name="grid1-color" id="grid1-color">
        </fieldset>
        <fieldset>
            <legend>Grid 2</legend>
            <p>Every <input type="number" name="" id=""> squares</p>
            <input type="color" name="grid2-color" id="grid2-color">
        </fieldset>
        <fieldset>
            <legend>Grid 3</legend>
            <p>Every <input type="number" name="" id=""> squares</p>
            <input type="color" name="grid3-color" id="grid3-color">
        </fieldset>
    </div>
</template>

<script>
export default {
  data () {
    return {
      pageSizePreset: 'preset',
      pageSizePresets: '8p5x11'
    }
  }
}
</script>

<style lang="scss" scoped>
    div {
        display: flex;
        flex-wrap: wrap;
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(20rem, 1fr))
    }
</style>
