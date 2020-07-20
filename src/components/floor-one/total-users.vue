<template>
  <common-card
    title="累计用户数"
    value="1,087,503"
  >
    <template>
      <v-chart :options="getOptions()"></v-chart>
    </template>
    <template v-slot:footer>
      <div class="total-users-footer">
        <span>日同比 </span>
        <span class="emphasis">8.73%</span>
        <span class="increase"></span>
        <span class="month">月同比 </span>
        <span class="emphasis">35.91%</span>
        <span class="decrease"></span>
      </div>
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
        grid: {
          top: 0, left: 0, bottom: 0, right: 0
        },
        xAxis: {
          type: 'value',
          show: false
        },
        yAxis: {
          type: 'category',
          show: false
        },
        series: [
          {
            type: 'bar',
            stack: '总量',
            data: [200],
            barWidth: 10,
            itemStyle: {
              color: '#45c946'
            }
          },
          {
            type: 'bar',
            stack: '总量',
            data: [250],
            itemStyle: {
              color: '#eee'
            }
          },
          {
            type: 'custom',
            data: [200],
            stack: '总量',
            renderItem: (params, api) => {
              const value = api.value(0)
              const endPoint = api.coord([value, 0])
              return {
                type: 'group',
                position: endPoint,
                children: [{
                  type: 'path',
                  shape: {
                    d: 'M0 767.909l512.029-511.913L1024 767.909 0 767.909z',
                    x: -5,
                    y: 10,
                    width: 10,
                    height: 10,
                    layout: 'cover'
                  },
                  style: {
                    fill: '#45c946'
                  }
                }, {
                  type: 'path',
                  shape: {
                    d: 'M1024 255.996 511.971 767.909 0 255.996 1024 255.996z',
                    x: -5,
                    y: -20,
                    width: 10,
                    height: 10,
                    layout: 'cover'
                  },
                  style: {
                    fill: '#45c946'
                  }
                }]
              }
            }
          }
        ]
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
.total-users-footer
  display flex
  align-items center
  .month
    margin-left 10px
</style>
