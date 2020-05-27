<template>
  <div id="app">
    <h3>Default</h3>
    <SearchBox />
    <h3>Language: en</h3>
    <SearchBox lng="en" />
    <h3>Language: arabic</h3>
    <SearchBox lng="arabic" />
  </div>
</template>

<script>
import SearchBox from './components/search-box'

export default {
  name: 'App',
  components: {
    SearchBox
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
h3 {
  text-align: left;
}
</style>
