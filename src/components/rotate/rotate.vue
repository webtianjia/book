<style lang="less" scoped>
  .rotate{
    display: inline-block;
    vertical-align: middle;
    text-align: center;
    .icon{
      transition: all .2s linear;
      transform-origin: center;
    }

  }
</style>
<template>
  <div class="rotate" :style="{}">
    <svg class="icon" :style="{'fontSize':size,'transform':`rotate(${rotate}deg)`}" aria-hidden="true">
      <use xlink:href="#icon-baitianmoshi"></use>
    </svg>
  </div>
</template>
<script>
  export default {
    props: {
      size: {
        type: Number,
        default: 12
      },
      rotate: {
        type: Number
      }
    },
    data () {
      return {}
    },
    watch:{

    },
    methods: {}
  }
</script>
