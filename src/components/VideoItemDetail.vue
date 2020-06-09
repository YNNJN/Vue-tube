<template>
  <div class="videoItemDetail">
    <p class='col-12 text-center'> {{ video.snippet.title }} </p> 
    <iframe
      width="640"
      height="360"
      :src="videoUrl"
      frameborder="0"
    >
    </iframe>
  </div>
</template>

<script>
export default {
  name: 'VideoItemDetail',
  props: {
    video: Object
  },
  computed: {
    videoUrl() {
      const videoId = this.video.id.videoId
      return `http://youtube.com/embed/${videoId}?&amp;vq=hd1080`
    }
  },
  methods: {

  },
}
</script>

<style>

</style>