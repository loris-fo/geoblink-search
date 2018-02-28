<template>
  <div id="app">
    <img class="ml-3 mt-3" src="./assets/logo.svg">
    <router-view :states="states"/>
  </div>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      states: null
    }
  },
  methods: {
    loadStates: function () {
      this.$http.get('http://localhost:3000/states').then(function (response) {
        this.states = response.body
      })
    }
  },
  created: function () {
    this.loadStates()
  }
}
</script>

<style>
body {
  background-color: #1e3650;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  height: calc(100vh - 80px);
}
</style>
