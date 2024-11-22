<template>
  <div
    class="image-player"
    :style="{
      width: `${totalWidth}px`,
      height: `${cardHeight}px`,
    }"
    @mouseenter="stopAnimate"
    @mouseleave="startAnimate"
  >
    <div
      v-for="(item, index) in showList"
      ref="cards"
      class="card"
      :key="index"
      :style="{
        width: `${cardWidth}px`,
        height: `${cardHeight}px`,
        left: `${index * (cardWidth + space) - cardWidth - space / 2}px`,
      }"
      @click="linkJump(item)"
    >
      <img
        v-if="item.src"
        class="img"
        :src="item.src"
        alt="item.label"
      >
      <span
        v-if="item.label"
        class="label"
        :style="{
          marginLeft: item.src ? '10px' : '0',
        }"
      >{{ item.label }}</span>
    </div>
  </div>
</template>

<script setup>
import { defineProps, onBeforeMount, computed, ref, onMounted } from 'vue';

const props = defineProps({
  dataList: {
    type: Array,
    default: () => [],
  },
  showNum: {
    type: Number,
    default: 10,
  },
  cardWidth: {
    type: Number,
    default: 200,
  },
  cardHeight: {
    type: Number,
    default: 60,
  },
  direction: {
    type: String,
    default: 'left',
  },
  space: {
    type: Number,
    default: 50,
  },
  speed: {
    type: Number,
    default: 1,
  }
});

const cards = ref([]);
const showList = ref([]);
let requestId = null;
let currentIndex = 0;
const totalWidth = computed(() => props.showNum * (props.cardWidth + props.space));

onBeforeMount(() => {
  initShowList();
});

onMounted(() => {
  animate();
});

function initShowList () {
  if (!props.dataList.length) return;

  let tempList = [];
  for (let i = 0; i < props.showNum + 2; i++) {
    tempList.push(props.dataList[i % props.dataList.length]);
  }
  currentIndex = props.direction === 'left'
    ? (props.showNum + 1) % props.dataList.length
    : 0;
  showList.value = tempList;
}

function linkJump(item) {
  if (item.link) {
    window.open(item.link, '_blank');
  }
}

function animate () {
  if (!props.dataList.length) return;

  cards.value.forEach(card => {
    const left = Number.parseInt(card.style.left);

    if (props.direction === 'left') {
      if (left <= -(props.cardWidth * 2 + props.space * 1.5)) {
        currentIndex = (currentIndex + 1) % props.dataList.length;
        showList.value.shift();
        showList.value.push(props.dataList[currentIndex]);
      } else {
        card.style.left = `${left - props.speed}px`;
      }
    } else {
      if (left >= (totalWidth.value + props.cardWidth + props.space * 1.5)) {
        currentIndex = (currentIndex - 1 + props.dataList.length) % props.dataList.length;
        showList.value.pop();
        showList.value.unshift(props.dataList.at(currentIndex));
      } else {
        card.style.left = `${left + props.speed}px`;
      }
    }
  });

  requestId = requestAnimationFrame(animate);
}

function stopAnimate () {
  requestId && cancelAnimationFrame(requestId);
  requestId = null;
}

function startAnimate () {
  !requestId && animate();
}
</script>

<style lang="less" scoped>
.image-player {
  position: relative;
  flex-shrink: 0;
  overflow: hidden;

  .card {
    position: absolute;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: rgba(238, 238, 238, 0.1);
    cursor: pointer;

    .img {
      max-height: 60%;
      max-width: 80%;
    }
  }

  .card:hover {
    background-color: rgba(238, 238, 238, 0.2);
  }
}
</style>