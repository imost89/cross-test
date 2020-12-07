<template>
  <div class="field">
    <cell
      v-for="number in 9"
      :key="number"
      :numberCell="number"
      :symbol="symbolView"
      @click-to-cell="clickToCell(number)"
    ></cell>
  </div>
</template>

<script>
import Cell from '@/components/cell'
import combos from '@/store/combos'

export default {
  name: "Field",
  components: {
    Cell
  },
  data () {
    return {
      symbolView: 'X',
      fieldArray: new Array(10)
    }
  },
  mounted () {
    console.log('mounted', combos)
  },
  methods: {
    clickToCell (numberCell) {
      console.log('field', numberCell)
      this.symbolView = this.symbolView === 'X' ? 'O' : 'X'
      this.fieldArray[numberCell] = this.symbolView
      combos.map(x => x)
      console.log('this.fieldArray', this.fieldArray)
    }
  }
}
</script>

<style scoped>
  .field {
    display: grid;
    grid-template-columns: auto auto auto;
    grid-template-rows: auto auto auto;
    border: red 2px solid;
    width: 100%;
    height: 100%;
  }
</style>
