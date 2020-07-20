<template>
  <div class="home">
    <floor-one></floor-one>
    <floor-two></floor-two>
    <floor-three></floor-three>
    <floor-four></floor-four>
  </div>
</template>

<script>
import FloorOne from '@/components/floor-one/floor-one'
import FloorTwo from '@/components/floor-two/floor-two'
import FloorThree from '@/components/floor-three/floor-three'
import FloorFour from '@/components/floor-four/floor-four'

export default {
  name: 'Home',
  components: {
    FloorOne,
    FloorTwo,
    FloorThree,
    FloorFour
  }
}
</script>

<style lang="stylus" scoped>
.home
  width 100%
  height 100%
  padding 20px
  background #eeeeee
  box-sizing border-box
</style>
