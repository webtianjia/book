<style lang="less" scoped>
  @import "../../assets/css/mixin";

  .list-heading {
    padding: 15px 13px 14px 13px;
    .border-1px(#f0f0f0);
    position: relative;
    .title {
      position: relative;
      font: bold 13px/13px a;
      color: rgba(0, 0, 0, .9);
      i {
        position: absolute;
        margin: -1px 0 0 5px;
        padding: 3px 3px 0px 3px;
        font: 9px/9px a;
        color: #fff;
        background-color: #53ac7d;
        border-radius: 1px;
      }
    }
    .tab {
      position: absolute;
      top: 9px;
      right: 13px;
      a {
        position: relative;
        padding: 16px 10px;
        font: 12px/12px a;
        color: #999;
        &:first-child:after {
          content: "";
          position: absolute;
          top: 16px;
          bottom: 16px;
          right: -2px;
          width: 1px;
          border-right: 1px solid #ccc;
        }
        &.active {
          color: #528ae8;
        }
      }
    }
  }
</style>
<template>
  <header class="list-heading border-1px">
    <div class="title">{{title}} <i v-show="recommend">推</i></div>
    <div class="tab" v-if="tab">
      <a href="javascript:" @click="type=1" :class="{'active':type==1}">{{desc.positive}}</a>
      <a href="javascript:" @click="type=2" :class="{'active':type==2}">{{desc.reverse}}</a>
    </div>
  </header>
</template>
<script>
  export default {
    props: {
      tab: {
        type: Boolean,
        default: false
      },
      recommend: {
        type: [Boolean, String],
        default: false
      },
      title: {
        type: String,
        required: true
      },
      desc: {
        type: Object,
        default () {
          return {
            positive: '男',
            reverse: '女'
          }
        }
      }
    },
    data () {
      return {
        type: 1
      }
    },
    methods: {}
  }
</script>
