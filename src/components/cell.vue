<template>
  <div
    class="cell"
    @click="clickToCell"
  >
    <slot>{{symbolView}}</slot>
  </div>
</template>

<script>
export default {
  name: "Cell",
  props: {
    numberCell: Number,
    symbol: String
  },
  data () {
    return {
      symbolView: ''
    }
  },
  methods: {
    clickToCell () {
      console.log('cell', this.numberCell, this.symbol)
      this.$emit('click-to-cell')
      this.symbolView = this.symbol
    }
  }
}
</script>

<style scoped>
  .cell {
    border: green 2px solid;
  }
</style>
