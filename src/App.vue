<template>
  <div id="app">
    <StateController/>
  </div>
</template>

<script>
import StateController from './components/StateController.vue'

export default {
  name: 'app',
  components: {
    StateController
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  font-size:20px;
  color: #2c3e50;
  margin-top: 20px;
}
</style>
