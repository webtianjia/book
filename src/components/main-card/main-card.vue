<style lang="less" scoped>
  @import "../../assets/css/mixin";

  .main-card {
    .card-heading {
      padding: 10px 14px;
      .border-1px(#f0f0f0);
      border-left: 6px solid #ffab18;
      .card-title {
        font-size: 16px;
        color: #333;
      }
    }
    .card-body {
      padding: 13px 14px 5px;
      .border-1px(#f0f0f0);
      .book-table {
        font-size: 0;
        .book-item {
          width: 32%;
          display: inline-block;
          vertical-align: top;
          margin-bottom: 8px;
          overflow: hidden;
          box-sizing: border-box;

          &:nth-child(3n-1) {
            margin: 0 2% 0 2%;
          }
          .book-cover {
            width: 100%;
            background-color: #eeece9;
            box-shadow: 0px 6px 5px -3px #aaa;
            border: 1px solid #f0f0f0;
            border-bottom: none;
            border-radius: 2px;
            overflow: hidden;
            .cover {
              width: 100%;
            }
          }
          .book-info {
            padding-top: 8px;
            .title {
              font-size: 13px;
              line-height: 1.4em;
              max-height: 2.8em;
              overflow: hidden;
              color: #8d8d8d;
            }
          }
        }
      }
    }
    .card-footer {
      .more {
        display: block;
        padding: 10px 0;
        text-align: center;
        font-size: 14px;
      }
    }
  }
</style>
<template>
  <section class="main-card">
    <div class="card-heading">
      <h1 class="card-title">本周最火</h1>
    </div>
    <div class="card-body border-1px">
      <ul class="book-table">
        <li class="book-item" v-for="i in 6">
          <div class="book-cover">
            <img class="cover"
                 src="http://cover.read.duokan.com/mfsv2/download/fdsc3/p01I66oHszK2/7CDwQEqR7CFkXT.jpg!s" alt="">
            <div class="tag"></div>
          </div>
          <div class="book-info">
            <h3 class="title">驭房有术</h3>
          </div>
        </li>
      </ul>
    </div>
    <div class="card-footer">
      <a class="more" href="#">查看更多</a>
    </div>
  </section>
</template>
<script>
  export default {
    data () {
      return {}
    },
    methods: {}
  }
</script>
