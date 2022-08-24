<template>
  <div id="app">
    <pass-word-checker></pass-word-checker>
  </div>
</template>

<script>
import PassWordChecker from './components/PassWordChecker.vue'

export default {
  name: 'app',
  components: {
    PassWordChecker
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
  display: flex;
  justify-content: center;  
}
</style>
