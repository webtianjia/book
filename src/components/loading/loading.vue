<style lang="less" scoped>
  @import "../../assets/css/animated";
  .loading {
    position: fixed;
    z-index: 10000;
    top:0;
    left: 0;
    width: 100%;
    bottom:0;
    box-sizing: border-box;
    background-color: hsla(0,0%,100%,.8);
    display: flex;
    align-items: center;
    justify-content: center;
    .loading-inner{
      position: relative;
      div {
        &:first-of-type {
          width: 0;
          height: 0;
          border: 25px solid #ff6001;
          border-right-color: transparent;
          border-radius: 25px;
          animation:rotate_pacman_half_up 0.5s 0s infinite
        }
        &:nth-child(2) {
          width: 0px;
          height: 0px;
          border: 25px solid #ff6001;
          border-right: 25px solid transparent;
          border-radius: 25px;
          margin-top: -50px;
          animation:rotate_pacman_half_down 0.5s 0s infinite
        }
        &:nth-child(3), &:nth-child(4), &:nth-child(5), &:nth-child(6) {
          background-color: #ff6001;
          width: 15px;
          height: 15px;
          border-radius: 100%;
          margin: 2px;
          width: 10px;
          height: 10px;
          position: absolute;
          transform: translate(0, -6.25px);
          top: 25px;
          left: 100px;
        }
        &:nth-child(3) {
          animation: pacman-balls 1s 0.33s infinite linear;
        }
        &:nth-child(4) {
          animation: pacman-balls 1s 0.66s infinite linear;
        }
        &:nth-child(5) {
          animation: pacman-balls 1s 0.99s infinite linear;
        }
      }
    }
  }
</style>
<template>
  <div class="loading">
    <div class="loading-inner">
      <div></div>
      <div></div>
      <div></div>
      <div></div>
      <div></div>
    </div>
  </div>
</template>
<script>
  export default {}
</script>
