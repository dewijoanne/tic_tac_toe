<template>
  <div id="app">
    <h1>Tic Tac Toe</h1>
    <router-view />
  </div>
</template>

<script>
export default {
  name: 'App',
  computed: {
    home () {
      return this.$store.state.home
    }
  },
  watch: {
    home () {
      if (this.home) {
        this.$store.commit('RESET_GAME')
        this.$router.push('/')
      }
    }
  }
}
</script>

<style>
body {
  margin: 20px;
  background-color: #001824;
  color: #f7f7f7;
}
body, button, input {
  font-family: 'Alegreya Sans', sans-serif;
  font-size: 24px;
  font-weight: 500;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
h1 {
  margin: 40px 0;
  font-size: 48px;
  line-height: 32px;
  font-weight: 700;
  color: #FEC500;
}
#app {
  text-align: center;
}
</style>
