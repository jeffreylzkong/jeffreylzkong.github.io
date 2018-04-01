<template>
  <div id="app">
    <header>
      <span>Madela <img class="bottle" src="./assets/feeding-bottle.svg"/>.com</span>
    </header>
    <main>
      <stop-watch1></stop-watch1>
      <stop-watch1></stop-watch1><stop-watch1></stop-watch1><stop-watch1></stop-watch1><stop-watch1></stop-watch1>
     <stop-watch-analog></stop-watch-analog>
    </main>
  </div>
</template>

<script>
import StopWatch1 from './components/StopWatch1'
import StopWatchAnalog from './components/StopWatchAnalog'

export default {
  name: 'app',
  components: {
    StopWatch1,
    StopWatchAnalog
  }
}
</script>

<style>
body {
  margin: 0;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

main {
  text-align: center;
  margin-top: 40px;
}

header {
  margin: 0;
  height: 56px;
  padding: 0 16px 0 24px;
  background-color: #35495E;
  color: #ffffff;
}

.bottle {
  width: 20px;
}

header span {
  display: block;
  position: relative;
  font-size: 20px;
  line-height: 1;
  letter-spacing: .02em;
  font-weight: 400;
  box-sizing: border-box;
  padding-top: 16px;
}
</style>
