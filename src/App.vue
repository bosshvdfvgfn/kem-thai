<template>
  <div id="app">
    <div>
      <video
        src="./assets/Output.mp4"
        playsinline
        style="pointer-events: none; width: 100vw; height: 60vh;"
        autoplay
        v-if="index === 0"
      ></video>

      <video
        playsinline
        style="pointer-events: none; width: 100vw; height: 60vh;"
        autoplay
        src="./assets/kem_seqA.mp4"
        v-if="index === 1"
      ></video>

      <video
        playsinline
        style="pointer-events: none; width: 100vw; height: 60vh;"
        autoplay
        src="./assets/kem_seqB.mp4"
        v-if="index === 2"
      ></video>
      <div class="btn-group" v-if="index === 0">
        <button class="btn-action" @click="onChangeVideo(2)">นึ่ง</button>
        <button class="btn-action" @click="onChangeVideo(1)">น้ำจิ้ม</button>
      </div>
      <div class="btn-group" v-if="index !== 0">
        <button class="btn-action" @click="onChangeVideo(0)">เล่นซ้ำ</button>
        <button class="btn-action" @click="redirect">ไปเว็บ</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data: function() {
    return {
      index: 0,
      listVideos: [
        "./assets/kem_first.mp4",
        "./assets/kem_seqA.mp4",
        "./assets/kem_seqB.mp4",
        "./assets/kem_mid_loop.mp4",
        "./assests/kem_first_end.mp4"
      ]
    };
  },
  methods: {
    onChangeVideo: function(index) {
      this.index = index;
    },
    redirect: function() {
      window.location.href = "https://www.thaihealth.or.th/";
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.btn-group {
  margin-top: 10%;
  display: flex;
  justify-content: space-around;
}

.btn-action {
  border-width: 0px;
  border-radius: 50%;
  padding: 10px 20px 10px 20px;
  background-color: rgb(232, 138, 177);
  color: white;
  font-size: 20px;
  cursor: pointer;
}

.btn-action:focus {
  outline: none;
}

video::-webkit-media-controls-play-button {
  display: none !important;
}
video::-webkit-media-controls-volume-slider {
  display: none !important;
}
video::-webkit-media-controls-mute-button {
  display: none !important;
}
video::-webkit-media-controls-timeline {
  display: none !important;
}
video::-webkit-media-controls-current-time-display {
  display: none !important;
}
</style>
