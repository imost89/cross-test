<template>
  <div id="app">
    <!--HelloWorld msg="Welcome to Your Vue.js App"/-->
    <div class="main-wrapper">
      <div class="main">
        <side-panel />
        <field />
      </div>
    </div>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import SidePanel from './components/side-panel'
import Field from './components/field'

export default {
  name: 'App',
  components: {
    // HelloWorld
    SidePanel,
    Field
  }
}
</script>

<style src="./style.css" lang="css" />
