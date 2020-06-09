<template>
  <div>
    <videoItemDetail
      @video-select="onVideoSelect"
      :video="video"
      v-for="video in videos"
      :key="video.etag"
    />
  </div>
</template>

<script>
import VideoItemDetail from './VideoItemDetail.vue'

export default {
  name: 'VideoItem',
  components: {
    VideoItemDetail
  },
  data() {
    return {
      video: {}
    }
  },
  props: {
    videos: Array,
  },
  methods: {

  },
}
</script>

<style>

</style>