<style scoped lang="less">
  .list-footer {
    display: flex;
    a {
      flex: 1;
      display: block;
      padding: 14px;
      font: 13px/1.3em a;
      text-align: center;
      color: rgba(0, 0, 0, .9);
      box-sizing: border-box;
      &:first-child {
        border-right: 1px solid #f0f0f0;
      }
    }
  }
</style>
<template>
  <footer class="list-footer">
    <a href="javascript:">换一换</a>
    <a href="javascript:">查看全部</a>
  </footer>
</template>
<script>
  export default {
    props:{

    },
    data () {
      return {}
    },
    methods: {}
  }
</script>
