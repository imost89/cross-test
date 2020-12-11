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
import combos from '@/store/combos.json'

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
      if (this.fieldArray[numberCell]) {
        return
      }
      this.fieldArray[numberCell] = this.symbolView
      if (combos.some(combo =>
        combo.every(index =>
          this.fieldArray[index] && this.fieldArray[combo[0]] === this.fieldArray[index]
        )
      )) {
        console.log(`${this.symbolView} win ^_^`)
      }
      this.symbolView = this.symbolView === 'X' ? 'O' : 'X'
    }
  }
}
</script>

<style src="./style.css" lang="css" />
