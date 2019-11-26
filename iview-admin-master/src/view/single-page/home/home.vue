<template>
  <div>
    <Row :gutter="20">
      <i-col :xs="12" :md="8" :lg="4" v-for="(infor, i) in inforCardData" :key="`infor-${i}`" style="height: 120px;padding-bottom: 10px;">
        <infor-card shadow :color="infor.color" :icon="infor.icon" :icon-size="36">
          <count-to :end="infor.count" count-class="count-style"/>
          <p>{{ infor.title }}</p>
        </infor-card>
      </i-col>
    </Row>
    <Row :gutter="20" style="margin-top: 10px;">
      <i-col :md="24" :lg="8" style="margin-bottom: 20px;">
        <Card shadow>
          <chart-pie style="height: 300px;" :value="pieData" text="支付渠道"></chart-pie>
        </Card>
      </i-col>
      <i-col :md="24" :lg="16" style="margin-bottom: 20px;">
        <Card shadow>
          <chart-bar style="height: 300px;" :value="barData" text="月交易金额"/>
        </Card>
      </i-col>
    </Row>
    <Row>
      <Card shadow>
        <example style="height: 310px;"/>
      </Card>
    </Row>
  </div>
</template>

<script>
import InforCard from '_c/info-card'
import CountTo from '_c/count-to'
import { ChartPie, ChartBar } from '_c/charts'
import Example from './example.vue'
export default {
  name: 'home',
  components: {
    InforCard,
    CountTo,
    ChartPie,
    ChartBar,
    Example
  },
  data () {
    return {
      inforCardData: [
        { title: '用户积分', icon: 'md-person-add', count: 2015, color: '#2d8cf0', p1: '用户名：BOC00004735', p2: '手机号：155****5057' },
        { title: '贡献值', icon: 'md-locate', count: 252, color: '#19be6b' },
        { title: '优惠额度', icon: 'md-help-circle', count: 300, color: '#ff9900' },
        { title: '累计优惠额度', icon: 'md-share', count: 195, color: '#ed3f14' },
        { title: '薅羊毛等级', icon: 'md-chatbubbles', count: 3, color: '#E46CBB' },
        { title: '黑名单', icon: 'md-map', count: 0, color: '#9A66E4' }
      ],
      pieData: [
        { value: 335, name: '买单吧App' },
        { value: 310, name: 'POS' },
        { value: 234, name: '微信' },
        { value: 135, name: '支付宝' },
        { value: 1548, name: '京东' },
        { value: 125, name: '手机银行' }
      ],
      barData: {
        五月: 13253,
        六月: 34235,
        七月: 26321,
        八月: 12340,
        九月: 24643,
        十月: 1322
      }
    }
  },
  mounted () {
    //
  }
}
</script>

<style lang="less">
.count-style{
  font-size: 50px;
}
</style>
