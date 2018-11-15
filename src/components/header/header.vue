<template>
<div class="header">
  <div>
    <div class="logo">
      <img src="./logo.png">
    </div>
    <div class="menu">
      <ul>
        <li><a>首页</a></li>
        <li class="about" @click.self="navToggle">
          关于用正
          <ul>
            <li><a>公司介绍</a></li>
            <li><a>企业文化</a></li>
            <li><a>服务优势</a></li>
            <li><a>企业荣耀</a></li>
          </ul>
        </li>
        <li class="server" @click.self="navToggle">
          我们的服务
          <ul>
            <li><a>临床监查与试验管理</a></li>
            <li><a>数据管理与生物统计</a></li>
            <li><a>药物警戒</a></li>
            <li><a>SMO</a></li>
            <li><a>注册事务</a></li>
            <li><a>医学事务</a></li>
            <li><a>生物等效性试验</a></li>
            <li><a>第三方稽查</a></li>
          </ul>
        </li>
        <li class="news" @click.self="navToggle">
          新闻中心
          <ul>
            <li><a>公司新闻</a></li>
            <li><a>行业新闻</a></li>
          </ul>
        </li>
        <li><a>人才招聘</a></li>
        <li><a>联系我们</a></li>
      </ul>
    </div>
    <div class="search">
      <a><input type="text" placeholder="站内搜索" id="keyword"></a>
      <a><img src="./search.png"></a>
    </div>
    <div>
      <Nav></Nav>
    </div>
  </div>
</div>
</template>
<script>
import Nav from './nav'

export default {
  components: {
    Nav
  },
  methods: {
    navToggle: function (event) {
      if (event.target.className.indexOf('navToggle') === -1) {
        event.target.className += ' navToggle'
      } else {
        event.target.className = event.target.className.replace(' navToggle', '')
      }
      console.log('eee')
    }
  }
}
</script>
<style lang='scss' scoped>
@media screen and (min-width: 1200px) {
  $headerHeight: 108px;
  @mixin dropDown($h) {
    height: $headerHeight;
    transition: height .3s;
    &:hover {
      height: $h;
    }
  }

  .header {
    border-top: #5986db solid 4px;
    border-bottom:#CCCCCC solid 1px;
  }
  .header>div {
    width: 1200px;
    position: relative;
    margin: 0 auto;
  }
  .logo {
    display: inline-block;
    height: $headerHeight;
    line-height: $headerHeight;
    img {
      width: 183px;
      height: 55px;
      vertical-align:middle;
    }
  }
  .menu {
    position: absolute;
    right: 70px;
    top: 0px;
  }
  .menu>ul>li {
    position: relative;
    vertical-align: top;
    font-size: 15px;
    height: $headerHeight;
    line-height: $headerHeight;
    padding: 0 38px;
    display: inline-block;
    cursor: pointer;
    overflow: hidden;
    &:hover {
      color: white;
    }
    &:hover::after {
      content: ' ';
      position: absolute;
      left: 0px;
      right: 0px;
      top: 0px;
      height: $headerHeight;
      background: #5986db;
      z-index: -1;
    }
  }
  .about {
    @include dropDown(280px);
  }
  .server {
    @include dropDown(452px);
  }
  .news {
    @include dropDown(194px);
  }
  .menu li ul {
    position: absolute;
    left: 0px;
    right: 0px;
  }
  .menu li li {
    display: block;
    background:rgba(89,134,219,0.8);
    height: 42px;
    line-height: 42px;
    border-top: white solid 1px;
    text-align: center;
    white-space:nowrap;
    font-size: 13px;
    color: white;
    &:hover {
      background:#5986db;
    }
  }
  .search {
    position: absolute;
    top: 34px;
    right: 0px;
    height: 36px;
    width: 36px;
    line-height: 30px;
    border: #c1c1c1 solid 1px;
    border-radius: 36px;
    background: white;
    overflow: hidden;
    z-index: 999;
    opacity:0.99;
    transition:width .3s;
    &:hover {
      width: 300px;
    }
    a:first-child {
      position: absolute;
      left: 8px;
      width:250px;
      display: inline-block;
      input {
        border: 0px white;
        outline:none;
        height: 30px;
        width: 250px;
      }
    }
    a:last-child {
      position: absolute;
      background: white;
      right: 0px;
      top: 5px;
      width: 36px;
      text-align: center;
      display: inline-block;
      cursor: pointer;
    }
    img {
      opacity:0.1;
      width: 25px;
      height: 25px;
    }
  }
  .nav {
    display: none;
  }
}
@media screen and (max-width: 1200px) {
  .header>div {
    position: relative;
    margin: 0 auto;
  }
  .logo {
    img {
      width: 100px;
      height: 30px;
      margin: 10px;
    }
  }
  .menu {
    position: fixed;
    height: 100%;
    width: 100%;
    background: rgba(29, 32, 136, 0.5);
    &>ul {
      position: relative;
      background: #1d2088;
      display: inline-block;
      height: 100%;
      width: 250px;
      overflow: hidden;
      &>li {
        height: 45px;
        line-height: 45px;
        color: white;
        padding-left: 12px;
        border-bottom: solid 1px white;
        ul {
          position: absolute;
          top: 0px;
          right: 0px;
          width: 0px;
          background: red;
          height: 100%;
          transition: all .2s;
          li {
            height: 45px;
            width: 100%;
            line-height: 45px;
            color: white;
            padding-left: 12px;
            border-bottom: solid 1px white;
            white-space:nowrap;
          }
        }
      }
      .navToggle {
        ul {
          width: 160px;
        }
        &::before {
          content: ' ';
          position: absolute;
          top: 0px;
          left: 0px;
          width: 90px;
          height: 100%;
          background: rgba(29, 32, 136, 0.5);
        }
      }
    }
  }
  .search {
    display: none;
  }
}
</style>
