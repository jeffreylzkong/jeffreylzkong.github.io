<template>
<div>
<div class="cute">
  <span>{{min}}</span>
  :
  <span>{{sec}}</span>
  :
  <span>{{milsec}}</span>
</div>
<div>
    <button @click="start" v-if="!isRunning">Start</button>
    <button @click="stop" v-else>Stop</button>
    <button @click="reset">Reset</button>
</div>
</div>
</template>

<script>
export default {
  name: 'StopWatch1',
  data(){
      return {
          tick: 0,
          timer: null,
          isRunning: false,
      }
  },
  computed: {
      milsec(){
        return this.twoDigit(this.tick % 100);
      },
      sec(){
        return this.twoDigit(parseInt(this.tick / 100));
      },
      min() {
        return this.twoDigit((this.tick / (100*60)).toFixed(0));
      },
  },
  methods: {
      twoDigit(val){
          if (val < 10) {
              return '0'+val;
          } else {
              return val;
          }
      },
      start(){
          this.timer = setInterval(()=>{
              this.tick += 1;
          }, 10);
          this.isRunning = true;
      },
      stop() {
          clearInterval(this.timer);
          this.isRunning = false;
      },
      reset() {
          if (this.isRunning) {
              this.stop();
          }
          this.tick = 0;
      }
  },

}
</script>

<style>
.cute {
    font-size: xx-small;
}
</style>
