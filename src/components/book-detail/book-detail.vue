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
      display: table;
      width: 100%;
      box-sizing: border-box;
      position: relative;
      overflow: hidden;
      .book-cover{
        width: 93px;
        height: 124px;
        margin-right: 18px;
        position: relative;
        background-color: #eeece9;
        box-shadow: 0px 6px 5px -3px #aaa;
        border: 1px solid #f0f0f0;
        border-bottom: none;
        overflow: hidden;
        img{
          width: 100%;
          height: 100%;
        }
        .tag{
          background-color: #49ab3f;
          font-size: 12px;
          position: absolute;
          top:0;
          left: 0;
          line-height: 1.4;
          color: #fff;
          width: 100%;
          transform-origin: top center;
          transform: translateX(50%) rotate(45deg) translateY(50%) scale(0.8);
          text-align: center;
          &:before{
            content:'\9650\514d';
          }
        }
      }
      .info{
        padding: 0;
        display:table-cell;
        vertical-align: middle;
        .title{
          margin-bottom: 13px;
          font-size: 1.6rem;
          overflow: hidden;
          font-weight: 400;
          color: #000;
        }
        .author{
          color: #4b99a7;
          line-height: 1.4;
          margin-top: 4px;
          font-size: 12px;
          span{
            display: inline-block;
            margin-right: 5px;
            line-height: 1.4;
            color: #4b99a7;

          }
        }
        .grade{
          line-height: 1;
          .star{
            display: inline-block;
            font-size: 0;
             width: 80px;
            vertical-align: middle;
            .icon{
              line-height: 1em;
              vertical-align: middle;
              font-size: 12px;
              margin-right: 5px;
              &:last-child{
                margin-right: 0;
              }
              color: #ff8c05;
            }
          }
          .read{
            vertical-align: middle;
            margin-top: 4px;
            font-size: 12px;
            color: #8d8d8d
          }
        }
        .count{
          color: #6e6e6e;
          font-size: 12px;
          .serial{
            color: #63bd6e;
            border-color: #63bd6e;
            border-radius: 4px;
            font-size: 12px;
            line-height: 16px;
            display: inline-block;
            transform: scale(.83);
            padding: 0 2px;
          }
        }
      }
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
    .book-tags{
      .title{
        font-size: 16px;
        font-weight: normal;
        color: #8d8d8d;
        padding: 14px 14px 8px;
      }
      .cnt{
        position: relative;
        line-height: 1.6;
        padding: 0 14px;
        margin-bottom: 10px;
        font-size: 14px;
        color: #585858;
        .tags{
          line-height: 1;
          overflow: hidden;
          .tag-item{
            display: inline-block;
            width: auto;
            line-height: 1.8em;
            padding: 0 20px;
            color: #766d5d;
            border-radius: 4px;
            background: #909da8;
            font-size: 14px;
            text-align: center;
            border:1px solid #d3d3d3;
            margin: 0 10px 5px 0;
            &:nth-child(3n+1){
              background-color: #fbebf8;
            }
            &:nth-child(3n+2){
              background-color: #fcedda;
            }
          }
        }
      }

    }
    .copyright{
      margin-bottom: 1px;
      .title{
        margin-bottom: 8px;
        font-size: 15px;
        font-weight: 400;
        padding: 15px 14px 0 14px;
        color: #8d8d8d;
      }
      .container{
        padding: 0 14px;
        margin-bottom: 12px;
        .text{
          color: #8d8d8d;
          line-height: 1.6;
          font-size: 14px;
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
                <div class="book-cover">
                  <img alt="魂帝武神" src="http://cover.read.duokan.com/mfsv2/download/fdsc3/p01Qq9kRVHCs/FdC5Z9uvJ1PVdM.jpg!s">
                  <div class="tag"></div>
                </div>
              <div class="info">
                <h3 class="title">魂帝武神</h3>
                <p class="author">
                  <span>小小八</span>
                </p>
                <div class="grade">
                    <div class="star">
                      <svg v-for="i in 5" class="icon" aria-hidden="true">
                        <use xlink:href="#icon-wujiaoxing"></use>
                      </svg>
                    </div>
                    <span class="read">94个评价</span>
                </div>
                <p class="count">
                  字数：188万字
                  <span class="serial">连载中</span>
                </p>
              </div>
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
            <div class="book-tags">
              <div class="title">
                <h3>类别标签</h3>
              </div>
              <div class="cnt">
                  <ul class="tags">
                    <li class="tag-item">现代言情</li>
                    <li class="tag-item">现代言情</li>
                  </ul>
              </div>
            </div>
            <split></split>
            <main-card title="作者其他图书"></main-card>
            <split></split>
            <div class="copyright">
                <div class="title">
                  <h1>图书信息</h1>
                </div>
              <div class="container">
                <ul class="text">
                  <li>版权：阅文集团旗下云起书院</li>
                </ul>
              </div>
            </div>
        </div>
        </div>
    </section>
  </transition>
</template>
<script>
  import BScroll from 'better-scroll'
  import bookCard from '../book-card/book-card.vue'
  import split from '../split/split.vue'
  import mainCard from '../main-card/main-card.vue'
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
      split,
      mainCard
    }
  }
</script>
