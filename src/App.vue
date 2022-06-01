<template>
  <Navbar />
  <div class="container">
    <router-view/>
  </div>
</template>

<script>
import Navbar from "./components/nav.vue"

export default {
  name: "App",
  components: {
    Navbar
  },
  mounted() {
    this.$store.commit("onStart")
  },
  watch: {
    $route() {
      this.$store.commit("onStart")
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
}

#nav a {
  font-weight: normal;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
