<template>
  <p>这是master分支</p>
  <Velocity msg="Welcome to Your Vue.js App"/>
</template>

<script>
import Velocity from './components/Velocity.vue'

export default {
  name: 'App',
  components: {
    Velocity
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
}
*{
  margin: 0;
  padding: 0;
}
</style>
