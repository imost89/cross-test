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
      this.$emit('click-to-cell')
      this.symbolView = this.symbolView ? this.symbolView : this.symbol
    }
  }
}
</script>

<style src="./style.css" lang="css" />
