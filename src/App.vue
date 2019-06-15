<template>
  <div id="app">
    <DataViz msg="THIS WILL THE TEXT ON MY PAGE"/>
  </div>
</template>

<script>
import DataViz from './components/DataViz.vue'

export default {
  name: 'app',
  components: {
    DataViz
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
