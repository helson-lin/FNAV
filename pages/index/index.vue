<template>
  <div class='home' :class="themeClass">
    <Slider/>
    <div class='container'>
    </div>
  </div>
</template>

<script>
import Slider from '../../components/Slider.vue';
export default {
  components: { Slider },
  data() {
    return {
      theme: 'red',
    }
  },
  computed: {
    themeClass() {
      return `theme-${this.theme}`;
    }
  }
}
</script>
<style lang='scss' scoped>

.home {
  height: 100vh;
  display: flex;
  .container {
    flex: 1;
    height: 100%;
    padding: 0 200px;
    box-sizing: border-box;
    @include background_color('bcc_color');
    img {
      width: 200px;
      height: 100px;
      display: inline-block;
      &:hover {
        content: url("https://pic.kblue.site/img/202201211447091.jpg");
      }
    }
    .img-li {
      width: 300px;
      height: 240px;
      background: url("https://pic.kblue.site/img/202201211447091.jpg"), radial-gradient(
          rgba(0,255,0,.8),
          black
      ),repeating-linear-gradient(
          transparent 0,
          rgba(0,0,0,.2) 3px,
          transparent 6px
      );
      background-size: cover;
      background-blend-mode: overlay;
    }
    @property --xPoint {
      syntax: '<length>';
      inherits: false;
      initial-value: 400px;
    }
    @property --yPoint {
      syntax: '<length>';
      inherits: false;
      initial-value: 300px;
    }

    .wrap {
      position: relative;
      margin: auto;
      width: 1000px;
      height: 600px;
      background:
        conic-gradient(
            from -45deg at var(--xPoint) var(--yPoint),
            hsla(170deg, 100%, 70%, .7),
            transparent 50%,
            hsla(219deg, 90%, 80%, .5) 100%),
        linear-gradient(-45deg, #060d5e, #002268);
      animation: pointMove 2.5s infinite alternate linear;
    }

    .shadow {
      position: absolute;
      top: -300px;
      left: -330px;
      width: 430px;
      height: 300px;
      background: #fff;
      transform-origin: 100% 100%;
      transform: rotate(225deg);
      clip-path: polygon(-100% 100%, 200% 100%, 200% 500%, -100% 500%);
      animation: scale 2.5s infinite alternate linear;
    }

    @keyframes scale {
      50%,
      100% {
        transform: rotate(225deg) scale(0);
      }
    }

    @keyframes pointMove {
      100% {
        --xPoint: 100px;
        --yPoint: 0;
      }
    }

  }
}
</style>
