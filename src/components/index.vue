<style scoped lang="less">
  @import '../assets/css/mixin';
  .index {
    .main {
      width: 100%;
      position: fixed;
      left: 0;
      bottom: 0;
      top: 44px;
      overflow: hidden;
    }
    .header-tab {
      padding: 0 90px;
      line-height: 44px;
      position: relative;
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
            &.icon-paihang {
              color: rgb(255, 148, 43);
            }
          }
        }
      }
    }
    .recommend {
      .recommend-heading {
        padding: 15px 13px 14px 13px;
        .border-1px(#f0f0f0);
        position: relative;
        .recommend-title {
          position: relative;
          font: bold 13px/13px a;
          color: rgba(0, 0, 0, .9);
          i {
            position: absolute;
            margin: -1px 0 0 5px;
            padding: 3px 3px 0px 3px;
            font: 9px/9px a;
            color: #fff;
            background-color: #53ac7d;
            border-radius: 1px;
          }
        }
        .tab {
          position: absolute;
          top: 9px;
          right: 13px;
          a {
            position: relative;
            padding: 16px 10px;
            font: 12px/12px a;
            color: #999;
            &:first-child:after {
              content: "";
              position: absolute;
              top: 16px;
              bottom: 16px;
              right: -2px;
              width: 1px;
              border-right: 1px solid #ccc;
            }
            &.active {
              color: #528ae8;
            }
          }
        }
      }
      .recommend-body {
        .border-1px(#f0f0f0);
        .list {
          padding: 0 13px;
          .item {
            padding: 17px 0;
            .border-1px(#f0f0f0);
            &:last-child{
              .border-no()
            }
            display: flex;
            .order {
              flex: 0 0 14px;
              width: 14px;
              margin-top: 1px;
              font: 13px/13px a;
              color: rgba(237, 83, 15, .9);
            }
            .info {
              flex: 1;
              margin-left: 20px;
              .title {
                position: relative;
                font: 15px/15px a;
                color: rgba(0, 0, 0, .9);
                background-color: #fff;
                .author{
                  position: absolute;
                  margin: 1px 0 0 13px;
                  font: 12px/12px a;
                  color: rgba(0,0,0,.4);
                  background-color: #fff;
                }
              }
            }
          }
        }
      }
      .recommend-footer{
        display: flex;
        a{
          flex: 1;
          display: block;
          padding: 14px;
          font:13px/1.3em a;
          text-align: center;
          color: rgba(0,0,0,.9);
          box-sizing: border-box;
          &:first-child{
            border-right: 1px solid #f0f0f0;
          }
        }
      }
    }
  }
</style>

<template>
  <div class="index">
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
          <use xlink:href="#icon-iconfontgerenzhongxin"></use>
        </svg>
      </a>
    </div>
    <main class="main" ref="main">
      <div class="container">
        <section class="top-home">
          <search-div></search-div>
          <div class="slide-banner">
            <div class="banner"><img class="cover"
                                     src="http://image.read.duokan.com/mfsv2/download/fdsc3/p01V1KHze11Q/lb3QSrqV6N2qpI.jpg"
                                     alt=""></div>
          </div>
          <ul class="top-btn-group">
            <li class="btn-item">
              <svg class="icon icon-jiage" aria-hidden="true">
                <use xlink:href="#icon-jiagexinxi"></use>
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
                <use xlink:href="#icon-leimupinleifenleileibie"></use>
              </svg>
              <p>分类</p>
            </li>
            <li class="btn-item">
              <svg class="icon icon-paihang" aria-hidden="true">
                <use xlink:href="#icon-paihang"></use>
              </svg>
              <p>排行</p>
            </li>
          </ul>
        </section>
        <split></split>
        <main-card @show_detail="showDateli"></main-card>
        <split></split>
        <section class="recommend">
          <div class="recommend-heading border-1px">
            <div class="recommend-title">重磅推荐 <i>推</i></div>
            <div class="tab">
              <a href="javascript:" @click="recommend_type=1" :class="{'active':recommend_type==1}">男</a>
              <a href="javascript:" @click="recommend_type=2" :class="{'active':recommend_type==2}">女</a>
            </div>
          </div>
          <div class="recommend-body border-1px">
            <ul class="list">
              <li class="item border-1px">
                <book-card></book-card>
              </li>
              <li v-for="i in 4" class="item border-1px">
                <span class="order">0{{i+1}}</span>
                <div class="info">
                  <div class="title">
                    异能狂徒在校园
                    <i class="author">
                      <span>三寸烟火</span>
                    </i>
                  </div>
                </div>
              </li>
            </ul>
          </div>
          <div class="recommend-footer">
            <a href="javascript:">换一换</a>
            <a href="javascript:">查看全部</a>
          </div>
        </section>
        <split></split>

      </div>
    </main>
    <book-detail  ref="book_detail" @startReading="startReading"></book-detail>
    <book-reader ref="book_reader"></book-reader>
    <loading style="display: none"></loading>
  </div>
</template>

<script>
  import searchDiv from './search-div/search-div.vue'
  import split from './split/split.vue'
  import mainCard from './main-card/main-card.vue'
  import BScroll from 'better-scroll'
  import bookCard from './book-card/book-card.vue'
  import bookDetail from './book-detail/book-detail.vue'
  import bookReader from './reader/reader .vue'
  import range from './range/range.vue'
  import loading from './loading/loading.vue'
  export default {
    name: 'index',
    data () {
      return {
        type: 1,
        recommend_type: 1,
        value: 0
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
      },
      showDateli (bookId) {
        this.$refs.book_detail.show()
      },
      startReading (bookId) {
        this.$refs.book_reader.show()
      }
    },
    components: {
      searchDiv,
      split,
      mainCard,
      bookCard,
      bookDetail,
      bookReader,
      range,
      loading
    }
  }
</script>

