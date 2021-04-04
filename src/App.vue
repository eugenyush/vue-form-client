<template>
  <div id="app">
    <FormClient/>
  </div>
</template>

<script>
import FormClient from './components/FormClient.vue'

export default {
  name: 'App',
  components: {
    FormClient
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background-color: #f7f7f7;
  padding: 30px;
}
</style>
