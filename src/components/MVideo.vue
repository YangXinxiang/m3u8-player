<template>
  <div class="container">
    <h2>测试播放m3u8视频</h2>
    <div class="player">
      <div v-if="src === ''">视频播放失败，无src</div>
      <video-player
        v-else
        class="video-player vjs-custom-skin"
        ref="videoPlayer"
        :playsinline="true"
        :options="playerOptions"
      ></video-player>
    </div>
  </div>
</template>

<script>
import "video.js/dist/video-js.css";
import "vue-video-player/src/custom-theme.css";


import "videojs-contrib-hls";
export default {
  props: {
    src: {
      type: String,
      default:
        "https://media.peiyou.eaydu.com/record/live_speiyou_online/0371-BSmzjUz5YAdKA6uSjM8Hgf/hls/0371-BSmzjUz5YAdKA6uSjM8Hgf-0371-BSmzjUz5YAdKA6uSjM8Hgf_5_LECTURE-0.m3u8",
    },
  },
  watch: {
    src: {
      handler(newval) {
        console.log('src change handler enter, newval = ', newval);
        this.playerOptions.sources[0].src = newval;
        this.srcvideo = newval;
      },
    },
  },
  created() {
    this.playerOptions.sources[0].src = this.src;
  },
  data() {
    return {
      srcvideo: "", //视频地址
      playerOptions: {
        //playbackRates: [0.7, 1.0, 1.5, 2.0], //播放速度

        autoplay: true, //如果true,浏览器准备好时开始回放。
        muted: false, // 默认情况下将会消除任何音频。
        loop: false, // 导致视频一结束就重新开始。
        preload: "auto", // 建议浏览器在<video>加载元素后是否应该开始下载视频数据。auto浏览器选择最佳行为,立即开始加载视频（如果浏览器支持）
        language: "zh-CN",
        aspectRatio: "16:9", // 将播放器置于流畅模式，并在计算播放器的动态大小时使用该值。值应该代表一个比例 - 用冒号分隔的两个数字（例如"16:9"或"4:3"）
        fluid: true, // 当true时，Video.js player将拥有流体大小。换句话说，它将按比例缩放以适应其容器。
        sources: [
          {
            type: "application/x-mpegURL",
            src: "https://media.peiyou.eaydu.com/record/live_speiyou_online/0371-BSmzjUz5YAdKA6uSjM8Hgf/hls/0371-BSmzjUz5YAdKA6uSjM8Hgf-0371-BSmzjUz5YAdKA6uSjM8Hgf_5_LECTURE-0.m3u8", //你的m3u8地址（必填）
          },
        ],
        // poster: 'poster.jpg', //你的封面地址
        width: document.documentElement.clientWidth,
        // notSupportedMessage: '此视频暂无法播放，请稍后再试' //允许覆盖Video.js无法播放媒体源时显示的默认信息。
        //  controlBar: {
        //   timeDivider: true,
        //   durationDisplay: true,
        //   remainingTimeDisplay: false,
        //   fullscreenToggle: true //全屏按钮
        //  }
      },
    };
  },
  components: {

  },
  methods: {
    //事件
  },
};
</script>

<style scoped>
.container {
  width: 800px;
  height: 600px;
}
</style>

