<template>
  <div class="scroll-list">
    <scroll-view class="scroll-view_H" :scroll-x="scrollX">
      <div class="content"  v-for="(item, index) in list" :key="item.id" @click="handleClick(index)">
        <h5 class="title">{{item.title}}</h5>
        <span class="subhead">{{item.subhead}}</span>
        <img :src="item.imgUrl" alt="" mode="aspectFill" >
      </div>
    </scroll-view>
  </div>
</template>

<script>
// import { showToast } from '@/utils/index'

export default {
  data () {
    return {
      scrollX: true
    }
  },
  props: {
    list: {
      type: Array,
      default: []
    }
  },
  mounted () {
    // console.log(this.list)
  },
  methods: {
    handleClick (index) {
      this.$emit('handleEnterClick', index)
    }
  }
}
</script>

<style lang="less" scoped>
.scroll-list{
  width: 100vw;
  overflow: hidden;
}
.scroll-view_H{
  width: 100%;
  white-space: nowrap;
}
.content{
  display: inline-block;
  height: 100px;
  width: 100px;
  margin: 10px;
  padding-bottom: 10px;
  background: #fff;
  overflow: hidden;
  h5{
    text-align:center;
    overflow:hidden;
    text-overflow:ellipsis;
    white-space:nowrap;
  }
  .subhead{
    display: block;
    font-size: 12px;
    text-align: center;
  }
  img{
    display: block;
    width: 90px;
    max-height: 80px;
    margin:0 auto;
    
  }
}
</style>
