<template>
  <div id="app">
    <PolygonComponent />
  </div>
</template>

<script>
import PolygonComponent from './components/PolygonComponent.vue'

export default {
  name: 'App',
  components: {
    PolygonComponent
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
