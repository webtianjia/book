<style scoped lang="less">
  @import '../assets/css/mixin';

  .index {
    overflow: hidden;
    .main {
      position: fixed;
      width: 100%;
      top: 44px;
      bottom: 0;
    }
    .header-tab {
      padding: 0 90px;
      line-height: 44px;
      position: relative;
      z-index: 999;
      text-align: center;
      background: #efeff0;
      .border-1px(#ddd);
      .tab {
        display: flex;
        .tab-item {
          flex: 1;
          font-size: 14px;
          a {
            padding-bottom: 12.7px;
          }
          &.active {
            a {
              .border-1px(#666);
              z-index: 100;
              color: #ff6001;
            }
          }
        }
      }
      .login-link {
        position: absolute;
        right: 0px;
        top: 0;
        padding: 0 12px;
        .icon {
          font-size: 20px;
        }
      }
    }
    .top-home {
      .slide-banner {
        .banner {
          width: 100%;
          line-height: 0;
          font-size: 0;
          background-color: #eeece9;
          .cover {
            width: 100%;
          }
        }
      }
      .top-btn-group {
        display: flex;
        margin: 14px 0 4px;
        width: 100%;
        .btn-item {
          flex: 1;
          line-height: 2.4;
          font-size: 12px;
          text-align: center;
          color: #555;
          .icon {
            font-size: 22px;
            &.icon-jiage {
              color: rgb(251, 86, 90);
            }
            &.icon-nv {
              color: rgb(242, 112, 167);
            }
            &.icon-nan {
              color: rgb(41, 201, 199);
            }
            &.icon-fenlei {
              color: rgb(45, 203, 116);
            }
            &.icon-paixing {
              color: rgb(255, 148, 43);
            }
          }
        }
      }
    }
  }
</style>
<template>
  <div class="index" >
    <div class="header-tab">
      <ul class="tab">
        <li class="tab-item  border-1px" @click="type=1" :class="{'active':type==1}">
          <a href="#">书城</a>
        </li>
        <li class="tab-item" @click="type=2" :class="{'active':type==2}">
          <a href="#">书架</a>
        </li>
      </ul>
      <a class="login-link" href="#">
        <svg class="icon" aria-hidden="true">
          <use xlink:href="#icon-user"></use>
        </svg>
      </a>
    </div>
    <div ref="main">
    <main class="main" >
      <section class="top-home">
        <search-div placeholder="search"></search-div>
        <div class="slide-banner">
          <div class="banner"><img class="cover"
                                   src="http://image.read.duokan.com/mfsv2/download/fdsc3/p01V1KHze11Q/lb3QSrqV6N2qpI.jpg"
                                   alt=""></div>
        </div>
        <ul class="top-btn-group">
          <li class="btn-item">
            <svg class="icon icon-jiage" aria-hidden="true">
              <use xlink:href="#icon-jiage"></use>
            </svg>
            <p>免费</p>
          </li>
          <li class="btn-item">
            <svg class="icon icon-nv" aria-hidden="true">
              <use xlink:href="#icon-nv"></use>
            </svg>
            <p>女生</p>
          </li>
          <li class="btn-item">
            <svg class="icon icon-nan" aria-hidden="true">
              <use xlink:href="#icon-nan"></use>
            </svg>
            <p>男生</p>
          </li>
          <li class="btn-item">
            <svg class="icon icon-fenlei" aria-hidden="true">
              <use xlink:href="#icon-fenlei"></use>
            </svg>
            <p>分类</p>
          </li>
          <li class="btn-item">
            <svg class="icon icon-paixing" aria-hidden="true">
              <use xlink:href="#icon-paixing"></use>
            </svg>
            <p>排行</p>
          </li>
        </ul>
      </section>
      <split></split>
      <main-card></main-card>
      <split></split>
      <section class="section"></section>
    </main>
    </div>
  </div>
</template>

<script>
  import searchDiv from './search-div/search-div.vue'
  import split from './split/split.vue'
  import mainCard from './main-card/main-card.vue'
  import BScroll from 'better-scroll'

  export default {
    name: 'index',
    data () {
      return {
        type: 1
      }
    },
    created () {
      this._initBScroll()
    },
    methods: {
      _initBScroll () {
        this.$nextTick(() => {
          this.scroll = new BScroll(this.$refs.main, {
            click: true
          })
        })
      }
    },
    components: {
      searchDiv,
      split,
      mainCard
    }
  }
</script>

