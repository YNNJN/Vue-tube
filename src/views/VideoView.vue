<template>
  <div class="VideoView container">
    <p class="lead text-center pt-5"><strong>영화 예고편 검색</strong></p>
    <VideoSearch @input-change="onInputChange"/>
    <div class="d-flex justify-content-center">
      <VideoItem :videos="videos"/>
    </div>
    <button v-if="videos.length > 0" @click="scrollToTop" class="button-bottom btn btn-outline-info">Top</button>
  </div>
</template>

<script>
const API_KEY = process.env.VUE_APP_YOUTUBE_API_KEY
const API_URL = 'https://www.googleapis.com/youtube/v3/search'
import axios from 'axios'
import VideoSearch from '@/components/VideoSearch'
import VideoItem from '@/components/VideoItem'

export default {
  name: 'VideoView',

  components: {
    VideoSearch,
    VideoItem,
  },
  data() {
    return {
      inputValue: '',
      videos: [],
    }
  },
  methods: {
    onInputChange(inputText) {
      this.inputValue = inputText + 'trailer'
      console.log(this.inputValue)
      axios.get(API_URL, {
        params: {
          key: API_KEY,
          part: 'snippet',
          type: 'video',
          q: this.inputValue
        }
      })
      .then(res => this.videos = res.data.items)
      .catch(err => console.error(err))
    },
    scrollToTop: function () {
      scroll(0,0)
    },
  },
}
</script>

<style>
.VideoView {
    margin: 20px;
    width: 40%;
    margin: 0 auto;
}

.button-bottom {
  position: fixed;
  right: 5vw;
  bottom: 3vh;
}

</style>