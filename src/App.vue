<template>
  <div id="app">
    <index-page></index-page>
  </div>
</template>

<script>
import IndexPage from "./components/pages/IndexPage"

export default {
  name: 'app',
  components: {
    IndexPage
  }
}
</script>

<style lang="scss">
html, body {
  margin: 0;
  padding: 0;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  max-width: 500px;
  min-height: 100vh;
  margin: 0 auto;
  box-shadow: 0 8px 16px rgba(123,138,147,.25);
}
</style>
