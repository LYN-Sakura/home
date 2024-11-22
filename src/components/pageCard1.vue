<template>
  <div class="page page-first">
    <div style="display: flex; align-items: center">
      <img :src="logo" style="transform: translateY(3px)" />
      <div class="page-index-title">萧疏的个人网站</div>
    </div>
    <div class="page-index-link">
      <a href="https://h.163.com/" target="_blank">逆水寒手游</a>
      <a href="https://www.yjwujian.cn/" target="_blank">永劫无间</a>
      <a href="https://www.csgo.com.cn/" target="_blank">CSGO</a>
    </div>
  </div>
</template>

<script setup>
import logo from "../assets/imgs/logo.svg";
</script>

<style scoped lang="less">
.page-first {
  flex-direction: column;
  color: #eee;
  background: url(../assets/imgs/backimg1.jpg) no-repeat fixed center 0% / cover;

  .page-index-title {
    font-size: 48px;
    margin-left: 20px;
  }
  .page-index-link {
    margin-top: 48px;
  }
  .page-index-link a {
    color: #eee;
    margin: 0 10px;
  }
  .page-index-link a:hover {
    color: #fa0;
    transition: color 0.4s linear;
  }
  img {
    width: 80px;
  }
}
</style>
