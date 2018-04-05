// 三条横杆的导航按钮，按钮的父元素position属性必须是absolute或relative
<template>
<div class="nav" @click="navToggle">
  <span></span>
</div>
</template>
<script>
export default {
  methods: {
    navToggle: function (event) {
      if (event.target.className === 'nav') {
        event.target.className = 'nav navToggle'
      } else {
        event.target.className = 'nav'
      }
    }
  }
}
</script>
<style lang='scss' scoped>
  $navWidth: 22px; // 横杆宽度
  $navHeight: 2px; // 横杆高度
  $navColor: red; // 横杆颜色
  $space: 6px; // 横杆间距
  $top: 10%; // 按钮距顶部距离
  $right: 12px; // 按钮距右边距离
  .nav {
    position: absolute;
    top: $top;
    right: $right;
    width: 35px;
    height: 35px;
    transition: transform .5s;
    span {
      position: absolute;
      display: inline-block;
      width: $navWidth;
      height: $navHeight;
      top: 50%;
      bottom: auto;
      left: 50%;
      right: auto;
      transform: translateX(-50%) translateY(-50%);
      background: $navColor;
      margin: 0 auto;
      pointer-events:none;
      &::after {
        position: absolute;
        content: " ";
        top: $space;
        width: $navWidth;
        height: $navHeight;
        background: $navColor;
        transition: transform .5s;
        pointer-events:none;
      }
      &::before {
        position: absolute;
        content: " ";
        top: -$space;
        width: $navWidth;
        height: $navHeight;
        background: $navColor;
        transition: transform .5s;
        pointer-events:none;
      }
    }
  }
  .navToggle {
    transform: rotate(180deg);
    & span::after {
      width: 13px;
      right: 0px;
      top: 5px;
      transform: rotate(-45deg);
    }
    & span::before {
      width: 13px;
      right: 0px;
      top: -5px;
      transform: rotate(45deg);
    }
  }
</style>
