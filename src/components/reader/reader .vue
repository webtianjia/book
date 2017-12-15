<style scoped lang="less">
  .reader {
    width: 100%;
    position: fixed;
    top: 0;
    left: 0;
    bottom: 0;
    overflow: hidden;
    .top {
      position: relative;
      top: 0;
      left: 0;
      right: 0;
      height: 45px;
      font: 14px/45px a;
      color: #d5d5d6;
      background-color: rgba(0, 0, 0, .9);
      z-index: 2;
      display: flex;
      .back{
        flex: 0 0 44px;
        font: 24px/44px a;
        text-align: center;
      }
      .more{
        position: absolute;
        right: 0;
        top:0;
        width: 44px;
        height: 44px;
        text-align: center;
        font: 24px/44px a;
        .icon{
          color: #fff;
        }
        .reader-popup{
          display: block;
          margin-top: 30px;
          position: relative;
          .popup-body{
            position: absolute;
            right:-12px;
            background: ;
          }
        }
      }
    }
  }
</style>
<template>
  <section class="reader ">
    <header class="top">
      <a class="back">
        <svg class="icon" aria-hidden="true">
          <use xlink:href="#icon-40"></use>
        </svg>
      </a>
      返回
      <a class="more">
        <svg class="icon" aria-hidden="true">
          <use xlink:href="#icon-gengduo"></use>
        </svg>
        <div class="reader-popup">
            <div class="popup-body border-1px">
                <div class="book">
                  <book-card></book-card>
                </div>
                <div class="autopay-check">
                <svg class="icon" aria-hidden="true">
                  <use xlink:href="#icon-yes"></use>
                </svg>
                自动购买下一章
              </div>
            </div>

        </div>
      </a>
    </header>
    <div></div>
  </section>
</template>
<script>
  import bookCard from '../book-card/book-card.vue'
  export default {
    name: 'reader',
    data () {
      return {}
    },
    methods: {},
    components: {
      bookCard
    }
  }
</script>
