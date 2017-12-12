
<style scoped lang="less">
  @import '../assets/css/mixin';
  .index{
      .header-tab{
        padding: 0 90px;
        line-height: 44px;
        position: relative;
        text-align: center;
        background: #efeff0;
        .border-1px(#ddd);
        .tab{
          display: flex;
          .tab-item{
            flex: 1;
            font-size: 14px;
            a{
              padding-bottom: 12.7px;
            }
            &.active{
              a{
                .border-1px(#666);
                z-index: 100;
                color: #ff6001;
              }
            }
          }
        }
        .login-link{
          position: absolute;
          right: 0px;
          top:0;
          padding:0 12px;
          .icon{
            font-size: 20px;
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
              <a href="#">主要</a>
            </li>
            <li class="tab-item" @click="type=2" :class="{'active':type==2}">
              <a href="#">次要</a>
            </li>
          </ul>
          <a class="login-link" href="#">
              <svg class="icon" aria-hidden="true">
                  <use xlink:href="#icon-user"></use>
              </svg>
          </a>
        </div>
  </div>
</template>

<script>
export default {
  name: 'index',
  data () {
    return {
      type: 1,
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

