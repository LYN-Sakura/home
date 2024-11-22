<template>
  <div class="page page-contact">
    <div class="page-contact-content">
      <a-timeline mode="alternate" labelPosition="relative">
        <a-timeline-item label="2018-07-02" dotColor="#c9cdd4">
          <img :src="mrtech" alt="" />
          <div style="display: flex; flex-direction: column; margin-left: 10px">
            <span>每日互动网络科技股份有限公司</span>
            <span style="color: #86909c; font-size: 14px">前端开发工程师</span>
          </div>
        </a-timeline-item>
        <a-timeline-item label="2020-07-06" class="diy-left" dotColor="#c9cdd4">
          <div style="display: flex; flex-direction: column">
            <span>乐麦信息技术（杭州）有限公司</span>
            <span style="color: #86909c; font-size: 14px"
              >前端开发工程师，优秀员工</span
            >
          </div>
          <img :src="leqee" alt="" style="margin-left: 10px" />
        </a-timeline-item>
        <a-timeline-item label="2024-05-27">
          <img :src="jdec" alt="" />
          <div style="display: flex; flex-direction: column; margin-left: 10px">
            <span>襄阳九鼎昊天环保设备有限公司</span>
            <span style="color: #86909c; font-size: 14px">前端开发工程师</span>
          </div>
        </a-timeline-item>
      </a-timeline>
    </div>
    <div class="page-contact-foot">
      <div class="copyright">©2024 asikun.asia</div>
    </div>
  </div>
</template>

<script setup>
import jdec from "../assets/imgs/jdec.png";
import leqee from "../assets/imgs/leqee.png";
import mrtech from "../assets/imgs/mrtech.png";
</script>

<style scoped lang="less">
.page-contact {
  .page-contact-foot {
    position: absolute;
    height: 100px;
    left: 0;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    background: rgb(37, 40, 45);
    bottom: 0;
    color: #ccc;
    font-size: 12px;
    flex-direction: column;
  }

  .page-contact-content {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-bottom: 120px;
    width: 100%;
  }

  :deep(.arco-timeline) {
    width: 100%;

    .arco-timeline-item {
      height: 100px;
    }
  }

  :deep(.arco-timeline-item-content) {
    font-size: 16px;
    color: #666;
    display: flex;
    align-items: center;

    img {
      height: 48px;
      width: fit-content;
    }
  }

  :deep(.arco-timeline-item-label) {
    font-size: 14px;
  }

  :deep(.diy-left) {
    .arco-timeline-item-content-wrapper {
      padding-right: 0;
    }

    .arco-timeline-item-content {
      justify-content: flex-end;
    }
  }
}
</style>
