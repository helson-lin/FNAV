<template>
  <div class='tabs' :style="styleVar" >
    <div :class="['tab', index === aIndex ? 'active' : '', animate === 'slideDown' ? 'slideDown' : 'slideUp']" v-for='(tab,index) in list' :key='index' @click="changeTab(index)">{{tab}}</div>
  </div>
</template>
<script>
export default {
  name: 'Tab',
  data() {
    return {
      list: ['测试1', '测试2', '测试3', '测试4'],
      aIndex: 3,
      animate: 'slideDown',
      animateLen: 0,
      styleVar: {},
    }
  },
  methods: {
    changeTab(index) {
      if(index === this.aIndex) return;
      if(index > this.aIndex) {
        this.animate = 'slideDown';
        this.animateLen = -(index - this.aIndex) * 30;
      } else {
        this.animate = 'slideUp';
        this.animateLen = -(index - this.aIndex )* 30;
      }
      this.styleVar = {
        "--animate-length": `${this.animateLen}px`,
      };
      this.$nextTick(() => {
        this.aIndex = index;
      })
    }
  }
}
</script>
<style lang='scss' scoped>
@keyframes slideDown {
  0% {
    top: var(--animate-length);
    left: 0;
  }
  100% {
    top: 0;
    left: 0;
  }
}
@keyframes slideUp {
  0% {
    top: var(--animate-length);
    left: 0;
    z-index: 2;
  }
  100% {
    top: 0;
    left: 0;
    z-index: 2;
  }
}

.tabs {
  margin-top: 20px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  .tab {
    position: relative;
    display: inline-flex;
    line-height: 30px;
    cursor: pointer;
    @include font_color('fg-color');
    &::before {
      width: 4px;
      height: 30px;
      display: inline-block;
      content: '';
      background-color: #eee;
      margin-right: 10px;
    }
    &.slideDown {
      &::after {
        animation-name: slideDown;
      }
    }
    &.slideUp {
      &::after {
        animation-name: slideUp;
      }
    }
  }
  .active {
    @include font_color('f_color');
    &::after {
      position: absolute;
      left: 0;
      width: 4px;
      height: 30px;
      display: inline-block;
      content: '';
      @include background_color('theme-color');
      animation-duration: 500ms;
      animation-timing-function: ease-in-out;
      animation-fill-mode: forwards;
    }
  }
}
</style>
