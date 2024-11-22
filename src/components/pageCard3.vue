<template>
  <div class="page page-techinfo">
    <div class="page-techinfo-wrap">
      <ImagePlayer :data-list="frontList"></ImagePlayer>
      <ImagePlayer
        style="margin-top: 30px"
        :data-list="backList"
        direction="right"
      ></ImagePlayer>
    </div>
  </div>
</template>

<script setup>
import ImagePlayer from "./ImagePlayer.vue";
import arco from "../assets/imgs/frame/arco.svg";
import echarts from "../assets/imgs/frame/echarts.png";
import element from "../assets/imgs/frame/element.svg";
import less from "../assets/imgs/frame/less.svg";
import three from "../assets/imgs/frame/three.svg";
import ts from "../assets/imgs/frame/ts.svg";
import vite from "../assets/imgs/frame/vite.svg";
import vue from "../assets/imgs/frame/vue.svg";
import pinia from "../assets/imgs/frame/pinia.svg";
import koa from "../assets/imgs/frame/koa.svg";
import git from "../assets/imgs/frame/git.png";
import linux from "../assets/imgs/frame/linux.png";
import mysql from "../assets/imgs/frame/mysql.svg";
import nginx from "../assets/imgs/frame/nginx.svg";
import node from "../assets/imgs/frame/node.svg";
import php from "../assets/imgs/frame/php.svg";
import thinkphp from "../assets/imgs/frame/thinkphp.svg";

const frontList = [
  {
    label: "",
    src: arco,
    link: "https://arco.design/",
  },
  {
    label: "",
    src: echarts,
    link: "https://echarts.apache.org/",
  },
  {
    label: "",
    src: element,
    link: "https://element-plus.org/",
  },
  {
    label: "",
    src: less,
    link: "https://lesscss.org/",
  },
  {
    label: "ThreeJs",
    src: three,
    link: "https://threejs.org/",
  },
  {
    label: "Pinia",
    src: pinia,
    link: "https://pinia.vuejs.org/",
  },
  {
    label: "TypeScript",
    src: ts,
    link: "https://www.typescriptlang.org/",
  },
  {
    label: "Vite",
    src: vite,
    link: "https://cn.vitejs.dev/",
  },
  {
    label: "Vue",
    src: vue,
    link: "https://cn.vuejs.org/",
  },
];

const backList = [
  {
    label: "",
    src: koa,
    link: "https://koajs.com/",
  },
  {
    label: "",
    src: git,
    link: "https://git-scm.com/",
  },
  {
    label: "",
    src: linux,
    link: "https://www.linux.org/",
  },
  {
    label: "",
    src: mysql,
    link: "https://www.mysql.com/",
  },
  {
    label: "Nginx",
    src: nginx,
    link: "https://nginx.org/",
  },
  {
    label: "",
    src: node,
    link: "https://nodejs.org/",
  },
  {
    label: "PHP",
    src: php,
    link: "https://www.php.net/",
  },
  {
    label: "",
    src: thinkphp,
    link: "https://www.thinkphp.cn/",
  },
];
</script>

<style scoped lang="less">
.page-techinfo {
  color: #eee;
  background: url(../assets/imgs/backimg2.jpg) no-repeat fixed center 0% / cover;

  .page-techinfo-wrap {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 100%;
    mask-image: linear-gradient(
      to right,
      transparent,
      transparent 10%,
      #000 25%,
      #000 75%,
      transparent 90%,
      transparent
    );
    overflow: hidden;
  }
}
</style>
