<style scoped lang="less">
  @import "../../assets/css/mixin";
  @import "../../assets/css/animated";
  .reader {
    width: 100%;
    position: fixed;
    top: 0;
    left: 0;
    bottom: 0;
    overflow: hidden;
    z-index: 400;
    .animated-move();
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
      .back {
        flex: 0 0 44px;
        font: 24px/44px a;
        text-align: center;
      }
      .more {
        position: absolute;
        right: 30px;
        top: 0;
        width: 44px;
        height: 44px;
        text-align: center;
        font: 24px/44px a;
        .icon {
          color: #fff;
        }
        .reader-popup {
          display: block;
          margin-top: 6px;
          position: relative;
          text-align: left;
          .animated-move();
          &:before {
            content: '';
            display: block;
            margin: 0 auto;
            width: 0;
            height: 0;
            border: 8px solid transparent;
            border-top: 0;
            border-bottom-color: #000;
            opacity: 0.85;
          }
          .popup-body {
            position: absolute;
            right: -12px;
            width: 182px;
            background: rgba(0, 0, 0, .85);
            border-radius: 6px;
            .reader-book {
              overflow: hidden;
              padding: 12px 10px;
              .border-1px(#e5e5e5);
              .book-cover {
                height: 72px;
                width: 54px;
                float: left;
              }
              .book-title {
                color: #ddd;
                line-height: 1;
                font-size: 15px;
                margin: 14px 0 0 64px;
              }
              .book-author {
                color: #9d9d9c;
                line-height: 28px;
                font-size: 12px;
                margin: 0 0 0 62px;
              }
            }
            .autopay-check {
              padding: 10px;
              line-height: 0;
              &.active {
                .icon {
                  color: #ff7800;
                }
              }
              .icon {
                font: 18px/18px a;
                color: #676665;
              }
              .text {
                font: 14px/22px a;
                color: #676665;
              }
            }
          }
        }
      }
    }
    .reader-chapter {
      margin: 0 auto;
      padding: 15px 0;
      max-width: 900px;
      color: #333;
      overflow: hidden;
      z-index: 1;
      position: absolute;
      left: 0;
      right: 0;
      top: 0;
      bottom: 0;
      .chapter {
        .reader-content {
          margin: 0 15px;
          h1 {
            margin-bottom: 20px;
            .border-1px(#736357);
            font: 20px/31px a;
            color: #736357;
            letter-spacing: 2px;
          }
          p {
            text-indent: 2em;
            margin: .5em 0;
            text-align: justify;
            letter-spacing: 0;
            line-height: 24px;
            overflow: hidden;
          }
        }
        .reader-ad {
          margin-top: 50px;
          padding: 15px;
          background: #f7e6d9;
          overflow: hidden;
          position: relative;
          .reader-close {
            position: absolute;
            right: -4rem;
            top: -4rem;
            padding: 4rem;
            .icon {
              background-color: rgba(0, 0, 0, .5);
              border-radius: 0 0 0 100%;
              color: #fff;
              display: block;
              width: 2rem;
              line-height: 2rem;
              text-align: center;
              padding: 0 0 .5rem .5rem;
            }
          }
        }
      }

    }
    .footer {
      position: absolute;
      bottom: 0;
      left: 0;
      right: 0;
      background: rgba(0, 0, 0, .9);
      z-index: 2;
      .btn-group {
        display: flex;
        .btn-item {
          flex: 1;
          height: 70px;
          text-align: center;
          color: #fff;
          .icon {
            margin: 14px auto 9px;
            font-size: 18px;
          }
          .icon-name {
            font: 10px/22px a;
          }
          &.open {
            .icon {
              color: #f87500;
            }
          }
        }
      }
      .reader-font {
        display: block;
        height: 135px;
        position: absolute;
        left: 0;
        right: 0;
        bottom: 70px;
        background: rgba(0, 0, 0, .92);
        z-index: 2;
        text-align: left;
        > div {
          margin-top: 15px;
          padding: 5px 10px;
        }
        .font-size {
          span {
            margin: 0 20px 0 10px;
            font: 14px/21px a;
            color: #fff;
          }
          a {
            display: inline-block;
            margin: 0 5px;
            border: 1px solid #8c8c8c;
            border-radius: 16px;
            padding: 5px 40px;
            font: 13px/16px a;
            color: #fff;
          }
        }
        .font-bg {
          span {
            margin: 0 20px 0 10px;
            font: 14px/21px a;
            color: #fff;
          }
          a {
            display: inline-block;
            position: relative;
            vertical-align: middle;
            margin-left: 10px;
            width: 30px;
            height: 30px;
            border-radius: 15px;
            &.active {
              &:after {
                display: block;
              }
            }
            &:after {
              content: ' ';
              display: none;
              position: absolute;
              left: -2px;
              top: -2px;
              width: 32px;
              height: 32px;
              border: 1px solid #ff7800;
              border-radius: 16px;
            }
            &[data-bg='0'] {
              background: #0f1410;
            }
            &[data-bg='1'] {
              background: #f7eee5;
            }
            &[data-bg='2'] {
              background: #e9dfc7;
            }
            &[data-bg='3'] {
              background: #a4a4a4;
            }
            &[data-bg='4'] {
              background: #cdefce;
            }
            &[data-bg='5'] {
              background: #283548;
            }
          }
        }
      }
    }
    .reader-mask {
      position: absolute;
      left: 0;
      right: 0;
      top: 0;
      bottom: 0;
      background: none;
      z-index: 1;
    }
    [data-bg='0'] {
      background: #0f1410;
    }
    [data-bg='1'] {
      background: #f7eee5;
    }
    [data-bg='2'] {
      background: #e9dfc7;
    }
    [data-bg='3'] {
      background: #a4a4a4;
    }
    [data-bg='4'] {
      background: #cdefce;
    }
    [data-bg="5"] {
      color: #7685a2;
      background: #283548;
    }
    [data-night="true"] {
      color: #4e534f;
      background: #0f1410;
    }
    [data-night="false"] {
      color: #4e534f;
      background: #e9dfc7;
    }
    .brightness{
      display: flex;
      .reader-range{
        flex: 1;
      }
      .reader-rotate{
        flex:0 0 30px;
      }
    }
  }
</style>
<template>
  <transition name="move">
  <section class="reader " ref="reader" v-show="showFlag" :style="{'filter':`brightness(${brightness*.11+.4})`}">
    <main class="reader-chapter" :style="{'fontSize':fontSize+'px'}" :data-bg="Bgindex" :data-night="night">
      <ul class="chapter">
        <li>
          <div class="reader-content">
            <h1>第4章：被关了</h1>
            <p>回到叶家，叶炔直接像拎小猫一样，把迟早早扔进房间里，关上门。</p>
            <p>迟早早一见，不用想就知道她又被关禁闭了，想到之前她被关禁闭的日子，那是多么的难熬苦逼。</p>
            <p>她在叶家，最怕的惩罚就是被叶炔关禁闭，这一关，三天三夜不准出来，还不给饭吃，最多给她口水喝。</p>
            <p>顿时间，迟早早觉得，她的人生就这么完了。</p>
            <p>可是，她又不服输，赶紧扑过来拍着门板喊，“叶炔哥哥，你关我做什么？我知道，我不应该在课堂上画你，可是……那也是因为我太爱你，太想你了。”</p>
            <p>“喂，叶小二，把门打开啊！”</p>
            <p>“老公，我还没吃晚饭呢，你舍得让这么瘦小的我不吃饭变得更瘦小吗？”</p>
            <p>“……”</p>
            <p>门外站着的人，静默，神色淡然如冰，眉宇间仿佛透着一股不悦，亦或是厌烦，转身便离开。</p>
            <p>没想到，会碰到跟上来的薛容真。</p>
            <p>刚才见儿子拎小鸡似的把迟早早拖上楼，薛容真就觉得大事不好，肯定那丫头，又惹到他家叶小二了。</p>
            <p>于是这便急冲冲的跟上楼来看，结果就听到儿子冰冷的声音，“不许让她出来，也别给她饭吃。”</p>
            <p>说完，叶炔阔步离去。</p>
            <p>薛容真赶紧跟上儿子的步伐，“这是怎么了？早早又怎么惹到你了？”</p>
            <p>“她没惹到我，要高考了，给她空间学习！”</p>
            <p>叶炔突然停下脚步，回头看着母亲，“是您告诉她，她以后要成为我的妻子？”</p>
            <p>薛容真茫然的点了点头，“是，是啊！怎么？你不想让她当你老婆？”</p>
            <p>“妈，她还是个孩子，即将面临高考，您怎么跟她说这个？”</p>
            <p>薛容真一副不以为然的表情，“我们家又不需要早早考上好大学，找好工作来养活我们，你这么会赚钱，还要她那么辛苦做什么？叶二啊，难道你就不心疼她？”</p>
            <p>叶二是叶炔的小名，实际上，叶炔小时候很活泼的，自从母亲把迟早早接来家后，他就在她面装高冷，后来渐渐的，他就真的高冷贵了。</p>
            <p>“你们真是无理取闹，我叶炔的妻子，可能是她那种不知天高地厚，奶气都没断的小丫头吗？”</p>
            <p>叶炔疾言厉色，话音落下，甩手就走。</p>
            <p>留下的薛容真，一愣一愣的，半响都没反应过来。</p>
            <p>当真她做错了？他家叶二，不喜欢早早？</p>
            <p>可早早那丫头，很漂亮啊。</p>
            <p>薛容真叹气，他家儿子怎么就不喜欢她呢！</p>
            <p>……</p>
            <p>房间里的迟早早喊了几声，无果，她不想连着三天都待在房间里，也不想饿肚子，所以这会儿打电话搬救兵。</p>
            <p>唐家，跟叶家是世交，迟早早从小被唐家双胞胎，二少爷唐纨君，三小姐唐晩沅带着长大，跟他们的关系那叫一个铁。</p>
            <p>她每次遇到什么困难，只要一个电话，那对龙凤胎就会过来解救她。</p>
            <p>所以现在的迟早早，就打电话给唐晚沅。</p>
          </div>
          <div class="reader-ad">
            <div class="reader-close"><span class="icon">×</span></div>
          </div>
        </li>
      </ul>
    </main>
    <header v-show="mask" class="top">
      <a class="back" @click="hide">
        <svg class="icon" aria-hidden="true">
          <use xlink:href="#icon-40"></use>
        </svg>
      </a>
      返回
      <a class="more" @click="toggleMore">
        <svg class="icon" aria-hidden="true">
          <use xlink:href="#icon-gengduo"></use>
        </svg>
        <transition name="move">
          <div v-if="moreFlag" class="reader-popup">
            <div class="popup-body ">
              <div class="reader-book" @click="hide">
                <img class="book-cover"
                     src="http://cover.read.duokan.com/mfsv2/download/s010/p01I1zQew1EB/MEp59LJ9HQEJ7f.jpg!s" alt="">
                <h3 class="book-title">婚后相爱：腹黑老公爆萌妻</h3>
                <p class="book-author">一笑倾晨</p>
              </div>
              <div class="autopay-check" :class="{'active':autoPay}" @click.stop.parents="togglePay">
                <svg class="icon" aria-hidden="true">
                  <use xlink:href="#icon-yes"></use>
                </svg>
                <span class="text"> 自动购买下一章</span>
              </div>
            </div>
          </div>
        </transition>
      </a>
    </header>
    <footer v-show="mask" class="footer">
      <ul class="btn-group">
        <li class="btn-item">
          <svg class="icon" aria-hidden="true">
            <use xlink:href="#icon-mulu"></use>
          </svg>
          <p class="icon-name">目录</p>
        </li>
        <li class="btn-item" :class="{'open':fontFlag}" @click="toggleFont">
          <svg class="icon" aria-hidden="true">
            <use xlink:href="#icon-zitidaxiao"></use>
          </svg>
          <p class="icon-name">字体</p>
          <div v-show="fontFlag" class="reader-font" @click.stop.paren>
            <div class="brightness">
              <range class="reader-range" v-model="brightness"></range>
              <rotate class="reader-rotate" :size="24" :rotate="brightness"></rotate>
            </div>
            <div class="font-size">
              <span>字号</span>
              <a @click.stop="plusFont" href="javascript:" class="font-large">大</a>
              <a @click.stop="reduceFont" href="javascript:" class="font-smail">小</a>
            </div>
            <div class="font-bg">
              <span>背景</span>
              <a @click="toggleBg(1)" :class="{'active':Bgindex===1}" href="javascript:" data-bg="1"></a>
              <a @click="toggleBg(2)" :class="{'active':Bgindex===2}" href="javascript:" data-bg="2"></a>
              <a @click="toggleBg(3)" :class="{'active':Bgindex===3}" href="javascript:" data-bg="3"></a>
              <a @click="toggleBg(4)" :class="{'active':Bgindex===4}" href="javascript:" data-bg="4"></a>
              <a @click="toggleBg(5)" :class="{'active':Bgindex===5}" href="javascript:" data-bg="5"></a>
              <a @click="toggleBg(0)" :class="{'active':Bgindex===0}" href="javascript:" data-bg="0"></a>
            </div>
          </div>
        </li>
        <li class="btn-item" @click="toggleNight">
          <div v-if="night">
            <svg class="icon" aria-hidden="true">
              <use xlink:href="#icon-baitianmoshi"></use>
            </svg>
            <p class="icon-name">白天</p>
          </div>
          <div v-else>
            <svg class="icon" aria-hidden="true">
              <use xlink:href="#icon-yejianzhuanhuan"></use>
            </svg>
            <p class="icon-name">夜间</p>
          </div>
        </li>
        <li class="btn-item">
          <svg class="icon" aria-hidden="true">
            <use xlink:href="#icon-download"></use>
          </svg>
          <p class="icon-name">下载</p>
        </li>
      </ul>
    </footer>
    <div class="reader-mask" @click="toggleControl"></div>
  </section>
  </transition>
</template>
<script>
  import BScroll from 'better-scroll'
  import range from '../range/range.vue'
  import rotate from '../rotate/rotate.vue'
  export default {
    name: 'reader',
    data () {
      return {
        showFlag: false,
        autoPay: true,
        moreFlag: false,
        fontFlag: false,
        night: true,
        mask: false,
        fontSize: 17,
        Bgindex: 1,
        brightness: 1
      }
    },
    created () {
      this.$nextTick(() => {
        this.scroll = new BScroll(this.$refs.reader, {
          click: true
        })
      })
    },
    methods: {
      show () {
        this.showFlag = true
      },
      hide () {
        this.showFlag = false
      },
      togglePay () {
        this.autoPay = !this.autoPay
      },
      toggleMore () {
        this.moreFlag = !this.moreFlag
      },
      toggleControl () {
        this.mask = !this.mask
        this.moreFlag = false
        this.fontFlag = false
      },
      toggleFont () {
        this.fontFlag = !this.fontFlag
      },
      toggleNight () {
        this.night = !this.night
      },
      toggleBg (index) {
        this.Bgindex = index
      },
      plusFont () {
        if (this.fontSize > 21) return
        this.fontSize++
      },
      reduceFont () {
        if (this.fontSize < 12) return
        this.fontSize--
      }
    },
    components: {
      range,
      rotate
    }
  }
</script>
