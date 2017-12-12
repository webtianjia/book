<style>
  .split {
    width: 100%;
    height: 10px;
  }
</style>
<template>
  <div class="split" :style="{'background':color}"></div>
</template>
<script>
  export default {
    props: {
      color: {
        type: String,
        default: '#f5f5f5'
      }
    },
  }
</script>
