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
  <div class="rotate">
    <svg class="icon" :style="{'fontSize':size,'transform':`rotate(${currentValue}deg)`}" aria-hidden="true">
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
      value: {
        type: Number
      }
    },
    data () {
      return {
        currentValue: this.value
      }
    },
    watch: {
      value (val) {
        this.currentValue = val
      }
    }
  }
</script>
