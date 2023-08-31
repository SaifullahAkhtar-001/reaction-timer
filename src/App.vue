<template>
  <h1 class="text-6xl font-bold">Reaction Timer</h1>
  <button @click="start" v-if="!isPlaying"
    class="text-white mt-8 bg-teal-600 hover:bg-teal-700 focus:outline-none active:bg-teal-800 font-medium rounded-full text-sm px-8 py-2.5 text-center mb-2 dark:bg-teal-600 dark:hover:bg-teal-600 dark:focus:ring-teal-800">Start</button>
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
