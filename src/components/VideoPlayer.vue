<template>
<div>
    <v-container fluid>
        <v-row justify="center pa-md-4">
      <video class="video-js" ref="videoPlayer" width="800px">
          <!-- <source src="https://videojs-vr.netlify.app/samples/eagle-360.mp4" type="video/mp4"> -->
      </video>
      </v-row>
      </v-container>
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
