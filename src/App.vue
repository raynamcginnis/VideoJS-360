<template>
  <div id="app">
    <video-player :options="videoOptions"/>
    </div>
</template>

<script>
import VideoPlayer from './components/VideoPlayer.vue'

export default {
  name: 'App',
  components: {
    VideoPlayer
  }, 
  data() {
		return {
			videoOptions: {
				autoplay: false,
        controls: true,
        preload: auto,
				sources: [
					{
						src:
							"https://videojs-vr.netlify.app/samples/eagle-360.mp4",
						type: "video/mp4"
					}
				]
			}
		};
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
