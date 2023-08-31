<template>
  <h1 class="text-6xl font-bold">Reaction Timer</h1>
  <button @click="start" v-if="!isPlaying"
    class="text-white mt-8 bg-purple-700 hover:bg-purple-800 focus:outline-none active:bg-purple-900 font-medium rounded-full text-sm px-8 py-2.5 text-center mb-2 dark:bg-purple-600 dark:hover:bg-purple-700 dark:focus:ring-purple-900">Start</button>
  <Block v-if="isPlaying" :delay="delay"/>
</template>

<script>

import Block from './components/Block.vue'

export default {
  name: 'App',
  components: {
    Block
  },
  data() {
    return {
      isPlaying: false,
      delay: null,
    }
  },
  methods: {
    start() {
      this.isPlaying = true
      this.delay = 2000 + Math.random() * 5000
    }
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
.dis{
  background-color: lightslategray;
}
</style>
