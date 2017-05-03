<template>
  <div class="progress-box">
    <div v-for="item in progress">
      <p class="title">{{item.title}}<span class="percent">{{item.percent}}</span></p>
      <p class="progress-bg"><span class="progress-bar" :class="item.color" :style="'width:'+ item.percent*100 + '%'"></span></p>
    </div>
  </div>
</template>

<script>
  export default {
    props: ['progress'],
    data() {
      return {
      };
    },
  };
</script>

<style lang="less" scoped>
  .progress-box {
    .title {
      font-size: 12px;
    }
  }
  .percent {
    float: right;
  }
  .progress-bg {
    height: 5px;
    border-radius: 5px;
    background: #f0f3f4;
    overflow: hidden;
    margin-bottom: 5px;
  }
  .progress-bar {
    display: block;
    height: 100%;
    background: #2db7f5;
    &.green {
      background: #00cc66;
    }
  }
</style>
