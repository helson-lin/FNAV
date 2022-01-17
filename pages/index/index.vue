<template>
  <div class='home' :class="themeClass">
    <span class='txt'>shjo</span>
  </div>
</template>
<script>
export default {
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
//@import '../../assets/scss/_themeify.scss';

.home {
  .txt {
    color: #1e6ceb;
    @include font_color("f_color");
  }
}
</style>
