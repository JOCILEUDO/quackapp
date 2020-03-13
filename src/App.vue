<template>
  <div id="app">
      <img class="icon" :class="crescer ? 'crescer_pato' : '' " @click.prevent="playSound" src="/svg/duck.svg" alt="">
  </div>
</template>

<script>
export default {
  name: 'App',
  components: {
  },
  data(){
    return {
      crescer: false,
    }
  },
  methods:{
     playSound () {
      this.crescer = true;
        var audio = new Audio(`/sound/Duck-quack.mp3`);
        audio.play();

        audio.addEventListener('ended', () => {
          this.crescer = false;
        })
    }
  }
}
</script>

<style>

.crescer_pato{
  animation: crescer 0.5s;
}

@keyframes crescer{
  0% {
    width: 35%;
  }
  25% {
    width: 33%;
  }
  75% {
    width: 44%;
  }
  100% {
    width: 35%;
  }
}

#app {
  display: inline-flex;
  height: 100vh;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  max-width: 450px;
  width: 100%;
  background: url('/media/background.jpg');
}

.icon{
    width: 35%;
    display: flex;
    margin: auto auto auto;
}
</style>
