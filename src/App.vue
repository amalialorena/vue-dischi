<template>
  <div id="app">
    <Logo/>
    
    <Container/>
  </div>
</template>

<script>
import Container from './components/Container.vue';
import Logo from './components/Logo.vue'

export default {
  name: 'App',
  components: {
    Logo,
    Container
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  // text-align: center;
  // color: #2c3e50;
  // margin-top: 60px;
  height: 100vh;
}
body {
  background-color: #17212c;
}
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
</style>
