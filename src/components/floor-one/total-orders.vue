<template>
  <common-card
    title="累计订单量"
    value="2,157,420"
  >
    <template>
      <v-chart :options="getOptions()"></v-chart>
      <div id="total-orders-chart"></div>
    </template>
    <template v-slot:footer>
      <span>昨日订单量 </span>
      <span class="emphasis">2,000,000</span>
    </template>
  </common-card>
</template>

<script>
import commonCardMixin from '@/mixins/common-card-mixin.js'
export default {
  mixins: [commonCardMixin],
  methods: {
    getOptions () {
      return {
        xAxis: {
          type: 'category',
          show: false,
          boundaryGap: false
        },
        yAxis: {
          show: false
        },
        grid: {
          top: 0,
          left: 0,
          right: 0,
          bottom: 0
        },
        series: [
          {
            type: 'line',
            data: [620, 432, 220, 534, 790, 430, 220, 320, 532, 320, 834, 698, 530, 220, 620],
            areaStyle: {
              color: 'purple'
            },
            lineStyle: {
              width: 0
            },
            itemStyle: {
              opacity: 0
            },
            smooth: true
          }
        ]
      }
    }
  }
}
</script>
