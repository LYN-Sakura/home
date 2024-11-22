<template>
  <div class="page page-myinfo">
    <div class="page-myinfo-img">
      <img :src="myimg" />
      <div class="page-myinfo-img-mask"></div>
      <div class="page-myinfo-img-line"></div>
      <div class="page-myinfo-img-text">DO MORE<br />AND<br />SPEAK LESS</div>
    </div>
    <div class="page-myinfo-content">
      <div>
        <div class="myinfo-title">姓名</div>
        <div class="myinfo-text">韩永昊（John Han）</div>
      </div>
      <div>
        <div class="myinfo-title">职位</div>
        <div class="myinfo-text">前端开发工程师（Front-end Engineer）</div>
      </div>
      <div>
        <div class="myinfo-title">学历</div>
        <div class="myinfo-text">华中师范大学硕士（Master, CCNU）</div>
      </div>
      <div>
        <div class="myinfo-title">现居地</div>
        <div class="myinfo-text">湖北襄阳（Xiangyang, Hubei）</div>
      </div>
      <div>
        <div class="myinfo-title">邮箱</div>
        <div class="myinfo-text">mrht@qq.com</div>
      </div>
    </div>
  </div>
</template>

<script setup>
import myimg from "../assets/imgs/info/myimg-big.jpg";
</script>

<style scoped lang="less">
.page-myinfo {
  .page-myinfo-img {
    position: relative;
    font-size: 0;
  }
  .page-myinfo-img > img {
    width: 380px;
  }
  .page-myinfo-img-mask {
    width: 100%;
    height: 100%;
    position: absolute;
    background-color: #000;
    top: 0;
    left: 0;
    opacity: 0;
    transition: opacity 0.2s linear;
  }
  .page-myinfo-img-line {
    width: 0;
    height: 80%;
    border-top: 1px solid #eee;
    border-bottom: 1px solid #eee;
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    margin: auto;
    transition: width 0.2s linear;
  }
  .page-myinfo-img-text {
    line-height: 30px;
    text-align: center;
    color: #fa0;
    position: absolute;
    height: 90px;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    margin: auto;
    opacity: 0;
    transition: font-size 0.2s linear, opacity 0.2s linear;
  }
  .page-myinfo-img:hover .page-myinfo-img-mask {
    opacity: 0.4;
    transition: opacity 0.2s linear;
  }
  .page-myinfo-img:hover .page-myinfo-img-line {
    width: 80%;
    transition: width 0.2s linear;
  }
  .page-myinfo-img:hover .page-myinfo-img-text {
    font-size: 20px;
    opacity: 1;
    transition: font-size 0.2s linear, opacity 0.2s linear;
  }
  .page-myinfo-content {
    margin-left: 60px;
    color: #666;
  }
  .page-myinfo-content > div {
    padding: 15px 0;
    border-bottom: 1px dashed #fa0;
  }
  .page-myinfo-content > div:first-child {
    padding-top: 0px;
  }
  .myinfo-title {
    font-size: 22px;
  }
  .myinfo-text {
    margin-top: 10px;
  }
}
</style>
