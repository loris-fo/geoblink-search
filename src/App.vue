<template>
  <div id="app">
    <img src="./assets/logo.png">
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
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
