<template>
    <header class="status-bar">
      <Row>
        <i-col span="12" class="title-box">
          <h2>短视频推荐</h2>
          <p>内容分析诊断工具</p>
        </i-col>
        <i-col span="12" class="search-box">
          <Input icon="ivu-icon ivu-icon-search" placeholder="视频ID" style="width: 300px;"></Input>
        </i-col>
      </Row>
    </header> 
</template>

<script>
  export default {
    data() {
      return {
        value4: '',
      };
    },
  };
</script>

<style lang="less" scoped>
  .status-bar {
    background: #857ac2;
    padding: 10px 15px;
    color: #fff;
    .search-box {
      text-align: right;
      padding-top: 6px;
    }
  }
</style>
