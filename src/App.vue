<template>
  <nav>
    <router-link to="/about">Stage</router-link>
  </nav>
  <router-view/>
  <!-- <div>
    <AboutView/>
  </div> -->
</template>

<!-- <script lang="ts">
import AboutView from './views/AboutView.vue'

export default {
  components: {
    AboutView
  }
}
</script> -->

<style lang="less">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
nav {
  padding: 30px;
  a {
    font-weight: bold;
    color: #2c3e50;
    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>



