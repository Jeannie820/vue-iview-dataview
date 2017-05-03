<template>
  <div class="index-page">
    <header-bar></header-bar>
    <Row style="padding:20px 0;" type="flex" justify="space-between">
      <Col span="8" style="padding-right:5px;">
          <Card class="preview-card">
              <p slot="title">视频预览</p>
              <p slot="extra"><span class="upload-time">已上传29小时30分</span><span class="length-video">长度1分48秒</span></p>
              <video src=""></video>
              <Row class="author-box" type="flex" justify="center" align="middle">
                <Col span="4">
                  <img src="../assets/avatar.png">
                </Col>
                <Col span="20">
                  <p>哈哈哈哈哈</p>
                </Col>
              </Row>
          </Card>
      </Col>
      <Col span="8" style="padding:0 15px;">
          <Card class="show-index">
              <p slot="title">表现指数</p>
              <Radio-group slot="extra" v-model="timeType" type="button">
                <Radio label="所有时间"></Radio>
                <Radio label="短时（1小时）"></Radio>
                <Radio label="长时（1天）"></Radio>
              </Radio-group>
              <Row>
                <Col span="8">
                  <h2>10,521</h2>
                  <p>曝光总次数</p>
                </Col>
                <Col span="8">
                  <h2>3,213</h2>
                  <p>播放数</p>
                </Col>
                <Col span="8">
                  <h2>0.521</h2>
                  <p>综合质量分</p>
                </Col>
              </Row>
              <Row>
                <Col span="6">
                  <h2>812</h2>
                  <p>点赞数</p>
                </Col>
                <Col span="6">
                  <h2>322</h2>
                  <p>评论数</p>
                </Col>
                <Col span="6">
                  <h2>113</h2>
                  <p>关注数</p>
                </Col>
                <Col span="6">
                  <h2>81</h2>
                  <p>转发数</p>
                </Col>
              </Row>
              <Row>
                <Col span="6">
                  <h2>3.9%</h2>
                  <p>CTR</p>
                </Col>
                <Col span="6">
                  <h2>11.4%</h2>
                  <p>评论数</p>
                </Col>
                <Col span="6">
                  <h2>6.4%</h2>
                  <p>关注转化率</p>
                </Col>
                <Col span="6">
                  <h2>1.9%</h2>
                  <p>转发率</p>
                </Col>
              </Row>
          </Card>
      </Col>
      <Col span="8" style="padding-left:5px;">
          <Card>
              <p slot="title">流量历史</p>
              <e-charts :options="option" style="width: 100%; height: 250px;"></e-charts>
          </Card>
      </Col>
    </Row>
    <Row style="padding:0 0 20px;" class="part-II">
      <Col span="8">
        <Card :bordered="false">
          <p slot="title">流量分配</p>
          <Icon slot="extra" type="ios-arrow-thin-right"></Icon>
          <e-charts :options="circleOption" style="width: 100%; height: 200px;"></e-charts>
        </Card>
      </Col>
      <Col span="8">
        <Card :bordered="false" class="cold-start">
          <p slot="title">冷启动情况</p>
          <span slot="extra">未完成</span>
          <i-circle :percent="80" style="margin-top: 13px;">
            <span class="demo-i-circle-inner" style="font-size:24px;">80%</span>
          </i-circle>
          <p class="title">完成度</p>
        </Card>
      </Col>
      <Col span="8">
        <Card :bordered="false" class="status-part">
          <p slot="title">标签及状态</p>
          <p>置顶推荐<span class="label-grey label">并没有</span></p>
          <p>推荐视频触发条件<span class="label-red label">满足</span></p>
          <p>SPAM检测<span class="label-green label">OK</span></p>
          <p>黑白屏检测<span class="label-green label">OK</span></p>
          <p>有效状态<span class="label-warn label">过期</span></p>
        </Card>
      </Col>
    </Row>
    <Card class="part-III">
      <p slot="title">发布用户画像</p>
      <span slot="extra">+详细</span>
      <Row>
        <Col span="7" class="user-info">
          <Row>
            <Col span="5">
              <img src="../assets/avatar.png">
            </Col>
            <Col span="19">
              <h2>为ta变乖</h2>
              <p class="momoid">陌陌号：200000</p>
              <span class="label label-blue">男的</span>
              <span class="label label-yellow">Lv.54</span>
              <span class="label label-red">SVIP6</span>
            </Col>
          </Row>
        </Col>
        <Col span="7">
          <Card :bordered="false" class="user-progress">
            <p slot="title">用户分类画像</p>
            <Radio-group slot="extra" v-model="timeType" type="button">
              <Radio label="所有时间"></Radio>
              <Radio label="24小时"></Radio>
            </Radio-group>
            <Progress-bar :progress="progressObj"></Progress-bar>
            <p class="more">更多<Icon type="ios-arrow-thin-right"></Icon></p>
          </Card>
        </Col>
        <Col span="10" class="user-others">
          <Row>
            <Col span="4">
              <h4>城市</h4>
              <p>北京</p>
            </Col>
            <Col span="4">
              <h4>城市</h4>
              <p>北京</p>
            </Col>
            <Col span="4">
              <h4>城市</h4>
              <p>北京</p>
            </Col>
            <Col span="4">
              <h4>城市</h4>
              <p>北京</p>
            </Col>
          </Row>
        </Col>
      </Row>
    </Card>
    <Card style="margin: 20px 0;" class="show-list">
      <p slot="title">Item-CF Top结果</p>
      <Row type="flex" justify="space-between">
        <Col span="3">
          <span class="label label-red">分数0.78</span>
          <img src="../assets/avatar.png" height="200" width="96%" alt="">
          <p class="content">看哈哈哈哈</p>
        </Col>
        <Col span="3">
          <span class="label label-red">分数0.78</span>
          <img src="../assets/avatar.png" height="200" width="96%" alt="">
          <p class="content">看哈哈哈哈</p>
        </Col>
        <Col span="3">
          <span class="label label-red">分数0.78</span>
          <img src="../assets/avatar.png" height="200" width="96%" alt="">
          <p class="content">看哈哈哈哈</p>
        </Col>
        <Col span="3">
          <span class="label label-red">分数0.78</span>
          <img src="../assets/avatar.png" height="200" width="96%" alt="">
          <p class="content">看哈哈哈哈</p>
        </Col>
        <Col span="3">
          <span class="label label-red">分数0.78</span>
          <img src="../assets/avatar.png" height="200" width="96%" alt="">
          <p class="content">看哈哈哈哈</p>
        </Col>
        <Col span="3">
          <span class="label label-red">分数0.78</span>
          <img src="../assets/avatar.png" height="200" width="96%" alt="">
          <p class="content">看哈哈哈哈</p>
        </Col>
        <Col span="3">
          <span class="label label-red">分数0.78</span>
          <img src="../assets/avatar.png" height="200" width="96%" alt="">
          <p class="content">看哈哈哈哈</p>
        </Col>
        <Col span="3">
          <span class="label label-red">分数0.78</span>
          <img src="../assets/avatar.png" height="200" width="96%" alt="">
          <p class="content">看哈哈哈哈</p>
        </Col>
      </Row>
    </Card>  
    <Card style="margin: 20px 0;" class="show-list">
      <p slot="title">LFM 最近邻</p>
      <Row type="flex" justify="space-between">
        <Col span="3">
          <span class="label label-red">分数0.78</span>
          <img src="../assets/avatar.png" height="200" width="96%" alt="">
          <p class="content">看哈哈哈哈</p>
        </Col>
        <Col span="3">
          <span class="label label-red">分数0.78</span>
          <img src="../assets/avatar.png" height="200" width="96%" alt="">
          <p class="content">看哈哈哈哈</p>
        </Col>
        <Col span="3">
          <span class="label label-red">分数0.78</span>
          <img src="../assets/avatar.png" height="200" width="96%" alt="">
          <p class="content">看哈哈哈哈</p>
        </Col>
        <Col span="3">
          <span class="label label-red">分数0.78</span>
          <img src="../assets/avatar.png" height="200" width="96%" alt="">
          <p class="content">看哈哈哈哈</p>
        </Col>
        <Col span="3">
          <span class="label label-red">分数0.78</span>
          <img src="../assets/avatar.png" height="200" width="96%" alt="">
          <p class="content">看哈哈哈哈</p>
        </Col>
        <Col span="3">
          <span class="label label-red">分数0.78</span>
          <img src="../assets/avatar.png" height="200" width="96%" alt="">
          <p class="content">看哈哈哈哈</p>
        </Col>
        <Col span="3">
          <span class="label label-red">分数0.78</span>
          <img src="../assets/avatar.png" height="200" width="96%" alt="">
          <p class="content">看哈哈哈哈</p>
        </Col>
        <Col span="3">
          <span class="label label-red">分数0.78</span>
          <img src="../assets/avatar.png" height="200" width="96%" alt="">
          <p class="content">看哈哈哈哈</p>
        </Col>
      </Row>
    </Card>  
    <Card class="history-content">
      <p slot="title">事件历史</p>
      <Row>
        <Col span="8">  
          <Timeline>
            <Timeline-item color="green">
              <Icon type="trophy" slot="dot"></Icon>
              <span>现在</span>
            </Timeline-item>
            <Timeline-item color="green">
              <p class="time">5s ago</p>
              <p class="content">随机探索完成<Icon slot="extra" type="ios-arrow-thin-right"></Icon></p>
            </Timeline-item>
            <Timeline-item color="green">
              <p class="time">5s ago</p>
              <p class="content">随机探索完成<Icon slot="extra" type="ios-arrow-thin-right"></Icon></p>
            </Timeline-item>
            <Timeline-item color="red">
              <p class="time">5s ago</p>
              <p class="content">随机探索完成<Icon slot="extra" type="ios-arrow-thin-right"></Icon></p>
            </Timeline-item>
            <Timeline-item color="blue">
              <p class="time">5s ago</p>
              <p class="content">随机探索完成<Icon slot="extra" type="ios-arrow-thin-right"></Icon></p>
            </Timeline-item>
            <Timeline-item color="green">
              <Icon type="trophy" slot="dot"></Icon>
              <span>发布</span>
            </Timeline-item>
          </Timeline>
        </Col>
        <Col span="16">
          <Card class="show-result red">
            <p slot="title">Spam标注</p>
            <div class="show-content">
              {{ JSONcontent }}
            </div>
          </Card>
        </Col>
      </Row>
    </Card>
  </div>
</template>

<script>

import HeaderBar from '@/components/Header';
import ProgressBar from '@/components/Progress';
import ECharts from 'vue-echarts/components/ECharts';

require('echarts/lib/chart/line');
require('echarts/lib/chart/pie');
require('@/assets/less/common.less');

export default {
  name: 'hello',
  data() {
    return {
      timeType: '所有时间',
      progressObj: [{
        color: 'green',
        title: '跳舞',
        percent: 0.65,
      }, {
        color: 'blue',
        title: '搞笑',
        percent: 0.30,
      }],
      JSONcontent: JSON.stringify({
        color: 'blue',
        title: '搞笑',
        percent: 0.30,
      }, null, '\t'),
      option: {
        title: {
          text: '堆叠区域图',
        },
        tooltip: {
          trigger: 'axis',
          axisPointer: {
            type: 'cross',
            label: {
              backgroundColor: '#6a7985',
            },
          },
        },
        legend: {
          data: ['邮件营销', '联盟广告'],
        },
        toolbox: {
          feature: {
            saveAsImage: {},
          },
        },
        grid: {
          top: '2%',
          left: '0%',
          right: '0%',
          bottom: '0%',
          containLabel: true,
        },
        xAxis: [
          {
            type: 'category',
            boundaryGap: false,
            data: ['周一', '周二', '周三', '周四', '周五', '周六', '周日'],
          },
        ],
        yAxis: [
          {
            type: 'value',
          },
        ],
        series: [
          {
            name: '邮件营销',
            type: 'line',
            stack: '总量',
            areaStyle: { normal: {} },
            data: [120, 132, 101, 134, 90, 230, 210],
          },
          {
            name: '联盟广告',
            type: 'line',
            stack: '总量',
            areaStyle: { normal: {} },
            data: [220, 182, 191, 234, 290, 330, 310],
          },
        ],
      },
      circleOption: {
        title: {
          text: '某站点用户访问来源',
          subtext: '纯属虚构',
          x: 'center',
        },
        tooltip: {
          trigger: 'item',
          formatter: '{a} <br/>{b} : {c} ({d}%)',
        },
        legend: {
          orient: 'vertical',
          left: 'left',
          data: ['直接访问', '邮件营销', '联盟广告', '视频广告', '搜索引擎'],
        },
        series: [
          {
            name: '访问来源',
            type: 'pie',
            radius: '55%',
            center: ['50%', '60%'],
            data: [
              { value: 335, name: '直接访问' },
              { value: 310, name: '邮件营销' },
              { value: 234, name: '联盟广告' },
              { value: 135, name: '视频广告' },
              { value: 1548, name: '搜索引擎' },
            ],
            itemStyle: {
              emphasis: {
                shadowBlur: 10,
                shadowOffsetX: 0,
                shadowColor: 'rgba(0, 0, 0, 0.5)',
              },
            },
          },
        ],
      },
    };
  },
  components: { HeaderBar, ProgressBar, ECharts },
};
</script>

<style scoped>
</style>
