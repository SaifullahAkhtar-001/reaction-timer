<template>
  <div class="dark:bg-slate-900 min-h-screen pt-[60px]">
    <h1 class="text-6xl dark:text-teal-600 font-bold">Reaction Timer</h1>
    <button @click="start" v-if="!isPlaying"
      class="text-white mt-8 bg-teal-600 hover:bg-teal-700 focus:outline-none active:bg-teal-800 font-medium rounded-full text-sm px-8 py-2.5 text-center mb-2 dark:bg-teal-600 dark:hover:bg-teal-600 dark:focus:ring-teal-800">Start</button>
    <Block v-if="isPlaying" :delay="delay" @end="endGame" />
    <Result v-if="showResult" :score="score"/>
  </div>
</template>

<script>

import Block from './components/Block.vue'
import Result from './components/Result.vue'

export default {
  name: 'App',
  components: {
    Block,Result
  },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: 0,
      showResult: false,
    }
  },
  methods: {
    start() {
      this.isPlaying = true
      this.delay = 2000 + Math.random() * 5000
      this.showResult = false
    },
    endGame(reactionTime) {
      this.score = reactionTime
      this.isPlaying = false
      this.showResult = true
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
}
</style>
