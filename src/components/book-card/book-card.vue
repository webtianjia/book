<style lang="less" scoped>
  .book-card {
    display: flex;
    .book-cover {
      flex: 0 0 85px;
      height: 113px;
      position: relative;
      background-color: #eeece9;
      border-radius: 1px;
      overflow: hidden;
      img {
        width: 100%;
        height: 100%;
        border-radius: 1px;
      }
      .order {
        height: 17px;
        width: 12px;
        position: absolute;
        left: 3px;
        top: 0;
        padding: 5px 1px 0 1px;
        font-size: 8px;
        line-height: .8em;
        text-align: center;
        color: #fff;
        background-color: #ed530f;
      }
      .finish {
        position: absolute;
        bottom: 0;
        width: 100%;
        box-sizing: border-box;
        font: 10px/10px a;
        padding: 25px 7px 6px;
        color: #fff;
        background: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, .3));
      }
    }
    .book-body{
      padding:6px 0 0 20px;
      .title{
        margin-bottom: 4px;
        font: 16px/17px a;
        color: rgba(0,0,0,.9);
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
      }
      .author{
        margin-top: 8px;
        font: 12px/12px a;
        color:rgba(0,0,0,.7);
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
      }
      .summary{
        display: -webkit-box;
        margin: 8px 0 0;
        height: 2.8em;
        font: 12px/1.4em a;
        color:rgba(0,0,0,.6);
        overflow: hidden;
        text-overflow: ellipsis;
        -webkit-line-clamp: 2;
        -webkit-box-orient: vertical;
      }
      .tag-group{
        margin-top: 10px;
        padding-top: 3px;
        overflow: hidden;
        .tag{
          float: left;
          margin: -3px 7px 0 0;
          padding: 3px 6px 2px;
          max-width: 6em;
          font: 10px/11px a;
          color: #53ac7d;
          border-radius: 3px;
          border:1px solid #53ac7d;
          overflow: hidden;
          text-overflow:ellipsis;
          white-space: nowrap;
        }
      }
    }
  }
</style>
<template>
  <div class="book-card">
    <div class="book-cover">
      <img class="cover" src="http://cover.read.duokan.com/mfsv2/download/fdsc3/p01W18eqGFfh/LgKEIErAOki8Qm.jpg!s"
           alt="">
      <div class="order">1</div>
      <p class="finish">完结</p>
    </div>
    <div class="book-body">
        <h2 class="title">我的绝美女神老婆</h2>
        <p class="author">
          <span class="author">一笔烟云</span>
        </p>
      <p class="summary">身怀绝技的方少阳，带着对大都市的美好憧憬，本想投靠师娘，却当上了医院妇科的男医生，泡了个美女医生，误...</p>
      <ul class="tag-group">
        <li class="tag">都市情缘</li>
        <li class="tag">热血都市</li>
        <li class="tag">506万字</li>
      </ul>
    </div>
  </div>
</template>
<script>
  export default {
    props: {
      color: {
        type: String,
        default: '#f5f5f5'
      }
    }
  }
</script>
