<style lang="less" scoped>
  @import "../../assets/css/mixin";
  @import "../../assets/css/animated";
  .book-detail {
    width: 100%;
    position: fixed;
    top: 0;
    left: 0;
    bottom: 0;
    z-index: 300;
    background-color: #fff;
    .animated-move();
    .top {
      width: 100%;
      height: 44px;
      background: #efeff0;
      .border-1px(#ddd);
      display: flex;
      position: relative;
      z-index:30;
      font: 15px/45px a;
      color: rgba(0, 0, 0, .7);
      .top-back {
        flex: 0 0 42px;
        display: block;
        text-align: center;
        line-height: 44px;
      }
      .header-home {
        width: 44px;
        height: 44px;
        text-align: center;
        line-height: 44px;
        position: absolute;
        right: 0;
        top: 0;
      }
    }
    .detail{
      position: fixed;
      top: 44px;
      left: 0;
      bottom:0;
    }
    .card {
      padding: 30px 20px 30px 30px;
      width: 100%;
      box-sizing: border-box;
    }
    .book-dash {
      .wrap {
        padding: 0 14px;
        margin: 0 0 27px;
        .btn-group {
          width: 100%;
          display: flex;
          white-space: nowrap;
          .btn-item {
            flex: 1;
            height: 2.8em;
            &:first-child {
              margin-right: 2%;
            }
            a {
              display: block;
              font: 14px/2.8em a;
              text-align: center;
              border: 1px solid #ddd;
              border-radius: 4px;
              color: #737373;
              &.hot {
                background: #f35d02;
                border: 1px solid #e35109;
                color: #fff;
              }
            }
          }
        }
      }
    }
    .book-folder {
      .folder {
        padding: 0 14px;
        margin-bottom: 10px;
        font: 14px/1.6 a;
        color: #585858;
        display: -webkit-box;
        text-overflow: ellipsis;
        overflow: hidden;
        -webkit-line-clamp: 5;
        -webkit-box-orient: vertical;
      }
      .line {
        .border-1px(#ddd)
      }
      .folder-tail {
        text-align: center;
        font-size: 14px;
        color: #8d8d8d;
        .tail {
          padding: 10px 14px;
        }
      }
    }
  }
</style>
<template>
  <transition name="move">
    <section class="book-detail" v-if="showFlag">
        <div class="top">
          <a @click="hide" class="top-back" href="javascript:">
            <svg class="icon" aria-hidden="true">
              <use xlink:href="#icon-40"></use>
            </svg>
          </a>
          <span class="top-title">婚后相爱：腹黑老公爆萌妻</span>
          <a href="javascript:" class="header-home">
            <svg class="icon" aria-hidden="true">
              <use xlink:href="#icon-home"></use>
            </svg>
          </a>
        </div>
      <div class="detail" ref="detail">
        <div class="container" >
            <div class="card">
              <book-card></book-card>
            </div>
            <div class="book-dash">
              <div class="wrap">
                <ul class="btn-group">
                  <li class="btn-item">
                    <a @click="startReading" class="hot">开始阅读</a>
                  </li>
                  <li class="btn-item">
                    <a href="javascropt:">下载</a>
                  </li>
                </ul>
              </div>
            </div>
            <div class="book-folder">
              <div class="folder ">
                进城闯荡的小阿姨衣锦还乡，张禹的老妈心动了，决定让儿子前去投奔。不曾想，所谓的豪宅就是一个三十平米的出租屋，更为要命的是，小阿姨经营的房产中介都快交不上房租了。
                风水卖房、风水装修……张禹从乡下棺材铺王老头那里学来的奇门玄术竟然派上了用场，摇身一变成了王牌经纪人……
                兄弟、美女，买房吗？阴宅阳宅都有，包装修！
                【都市风水秘术！灵异小说中的新题材，非恐怖，适合各种口味！】
                本书书友群：149661050（已满），2群：597276660（感谢美女书友墨白提供），V群：291777277（需订阅认证）。
              </div>
              <div class="line border-1px"></div>
              <div class="folder-tail">
                <div class="tail">最新：第2014章 艾伦小姐 更新于 23小时前</div>
              </div>
            </div>
            <split></split>
          <book-card v-for="i in 10"></book-card>
        </div>
        </div>
    </section>
  </transition>
</template>
<script>
  import BScroll from 'better-scroll'
  import bookCard from '../book-card/book-card.vue'
  import split from '../split/split.vue'
  export default {
    data () {
      return {
        showFlag: false
      }
    },
    methods: {
      show () {
        this.showFlag = true
        this.$nextTick(() => {
          if (!this.scroll) {
            this.scroll = new BScroll(this.$refs.detail, {
              click: true
            })
          } else {
            this.scroll.refresh()
          }
        })
      },
      hide () {
        this.showFlag = false
      },
      startReading () {
        this.$emit('startReading', 1)
      }
    },
    components: {
      bookCard,
      split
    }
  }
</script>
