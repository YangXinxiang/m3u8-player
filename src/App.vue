<template>
  <div id="app">
    <MVideo :src = "m3u8src"/>
  </div>
</template>

<script>
import MVideo from './components/MVideo.vue'
export default {
  name: 'App',
  data() {
    return {
      m3u8src: 'https://media.peiyou.eaydu.com/record/live_speiyou_online/0371-BSmzjUz5YAdKA6uSjM8Hgf/hls/0371-BSmzjUz5YAdKA6uSjM8Hgf-0371-BSmzjUz5YAdKA6uSjM8Hgf_5_LECTURE-0.m3u8'
    }
    
  },
  components: {
    MVideo
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
</style>
