<template>
<div>
      <video class="video-js" ref="videoPlayer">
          <!-- <source src="https://videojs-vr.netlify.app/samples/eagle-360.mp4" type="video/mp4"> -->
          <!-- <source src="https://www.youtube.com/watch?v=Vi0G9OgwCys" type="video/mp4"> -->
      </video>
    </div>
</template>

<script>
import videojs from 'video.js'

export default {
  name: "VideoPlayer",
  props: {
        options: {
            type: Object,
            default() {
                return {};
            }
        }
    },
    data() {
        // do nothing until video loads
        return {
            player: null
        }
    },
        // once video loads and player is ready, the onPlayerReady is called
    mounted() {
        this.player = videojs(this.$refs.videoPlayer, this.options, function onPlayerReady() {
            console.log('onPlayerReady', this);
        })
    },
    beforeDestroy() {
        if (this.player) {
            this.player.dispose()
        }
    }

};
</script>

<style scoped></style>
