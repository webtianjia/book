<style lang="less" scoped>
  .top-search{
    margin: 10px 13px;
    padding: 0 10px;
    color: rgba(0,0,0,.4);
    font-size: 11px;
    line-height: 33px;
    border: 1px solid #f5f5f5;
    border-radius: 2px;
  }
</style>
<template>
  <div class="top-search">
    <svg class="icon" aria-hidden="true">
      <use xlink:href="#icon-search"></use>
    </svg>
    {{placeholder}}
  </div>
</template>
<script>
  export default {
    props: {
      placeholder: {
        type: String,
        default: '输入书名/作者/关键字'
      }
    }
  }
</script>
