<template>
  <v-app>
    <v-main>
      <VideoPlayer :options="videoOptions"/>
    </v-main>
  </v-app>
</template>

<script>
import VideoPlayer from './components/VideoPlayer';

export default {
  name: 'App',

  components: {
    VideoPlayer,
  },

  data() {
		return {
			videoOptions: {
				autoplay: false,
        controls: true,
				sources: [
					{
						src:
              "https://videojs-vr.netlify.app/samples/eagle-360.mp4",
              // "http://media.w3.org/2010/05/sintel/trailer.mp4",
						type: "video/mp4"
					}
				]
			}
		};
	}
};
</script>
