<template>
  <v-chart :options="options"></v-chart>
</template>

<script>
import 'echarts/extension/bmap/bmap'
export default {
  data () {
    return {
      options: {}
    }
  },
  mounted () {
    this.options = {
      bmap: {
        key: '8OULYGdy8T9POO8DDLl3BRoysKvAIW4R',
        center: [104.114129, 37.550339],
        zoom: 5,
        roam: false // 是否允许缩放

      }
    }
  }
}
</script>

<style>

</style>
