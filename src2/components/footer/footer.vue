<template>
<div>
  <div class="footer">
    <div>
      <div>
        <dd>
          <a>关于用正</a>
        </dd>
        <dt>
          <a>公司简介</a>
          <a>企业文化</a>
          <a>服务优势</a>
          <a>企业荣誉</a>
        </dt>
      </div>
      <div>
        <dd>
          <a>我们的服务</a>
        </dd>
        <dt>
          <a>临床监查与试验管理</a>
          <a>数据管理与生物统计</a>
          <a>药物警戒</a>
          <a>SMO</a>
          <a>注册事务</a>
          <a>医学事务</a>
          <a>生物等效性试验</a>
          <a>第三方稽查</a>
        </dt>
      </div>
      <div>
        <dd>
          <a>新闻中心</a>
        </dd>
        <dt>
          <a>公司新闻</a>
          <a>行业新闻</a>
        </dt>
      </div>
      <div>
        <dd>
          <a>关注我们</a>
        </dd>
        <dt>
          <img src="./follow.jpg">
        </dt>
      </div>
      <div class="contact">
        <img src="./weibo.jpg">
        <img src="./weixin.jpg">
        <img src="./qq.jpg">
        <p>电话：021-61138233</p>
        <p>邮箱：BD@yzcro.com</p>
        <p>地址：上海市徐汇区中山西路1600号宏汇国际广场A座11楼</p>
      </div>
    </div>
  </div>
  <div class="bottom">Copyright©2016-2018 用正医药版权所有 ALL RIGHTS RESERVED. 沪ICP备06030446号</div>
</div>
</template>
<style lang='scss' scoped>
.footer {
  background: #f9f9f9;
  padding: 50px 0;
  &>div {
    width: 1200px;
    margin: 0 auto;
    font-size: 14px;
    color: #777777;
    &>div {
      display: inline-block;
      width: 210px;
      vertical-align: top;
      &>dd {
        color: #333333;
        margin-bottom: 12px;
      }
    }
  }
  .contact {
    font-size: 0px;
    width: 220px;
    padding-left: 120px;
    border-left: solid 1px #e5e5e5;
    height: 250px;
    img {
      margin-right: 1px;
      margin-bottom: 8px;
    }
    &>p {
      font-size: 14px;
      height: 30px;
      line-height: 24px;
    }
  }
}
a {
  display: block;
  height: 28px;
  line-height: 28px;
}
img {
  max-width: 100px;
}
.bottom {
  background: #7d7d7d;
  height: 45px;
  line-height: 45px;
  color: #adadad;
  font-size: 12px;
  font-weight: bolder;
  text-align: center;
}
@media screen and (max-width: 1200px) {
  .footer {
    background: white;
    &>div {
      display: none;
    }
  }
}
</style>
