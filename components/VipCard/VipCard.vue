<template>
  <view class="card">
    <view class="cover">
      <view class="top"> 卡修无忧会员 </view>
      <view class="bg-line">

      </view>
      <view class="bot"> 全站知识库海量搜索查看 </view>
    </view>
    <view class="info">
      <view class="top">
        最低￥
        <text class="money"> 15 </text>
        /月
      </view>
      <view class="bot">
        <button class="btn">立即开通</button>
      </view>
    </view>
  </view>
</template>

<script>
export default {
  props: {
    item: {
      type: Object,
      default: () => {
        return {};
      },
    },
  },
  data() {
    return {};
  },
  created() {},
  methods: {},
};
</script>

<style lang="scss" scoped>
.card {
  display: flex;
  // flex-direction: column;
  align-items: center;
  margin-bottom: 14px;
  justify-content: space-between;
  padding: 0 16px;
  margin-left: 16px;
  margin-right: 16px;

  height: 108px;
  background: #f5e3cd;
  border-radius: 8px 8px 0px 0px;
  .cover {
    .top {
      font-weight: bold;
      font-size: 20px;
      color: #32312d;
    }
    .bg-line{
      height: 4px;
      width: 41px;
      background: linear-gradient(to right,#E6C2A0, #F6E4CF);
      margin: 2px 0 4px 0;
    }
    .bot {
      font-weight: 500;
      font-size: 14px;
      color: #31302c;
    }
  }
  .info {
    margin-left: 11px;
    // flex: 1;
    display: flex;
    flex-direction: column;
    justify-content: space-between;

    .top {
      font-weight: 500;
      font-size: 13px;
      color: #131d34;
      margin-bottom: 6px;

      .money {
        font-weight: bold;
        font-size: 20px;
        color: #32312d;
        line-height: 40px;
      }
    }

    .tag {
      background: rgba(23, 122, 250, 0.1);
      border-radius: 3px 3px 3px 3px;
      width: fit-content;
      margin-right: 4px;
      font-size: 10px;
      color: #177afa;
      padding: 2px 6px;
    }

    .time {
      font-weight: 500;
      font-size: 11px;
      color: #818ca4;
      margin-bottom: auto;
      //   margin-bottom: 17px;
    }

    .bot {
      display: flex;
      justify-content: space-between;
      // align-items: center;
      align-items: flex-end;
      width: 100%;

      .btn {
        margin: 0;
        height: 26px;
        color: #fff;
        width: fit-content;
        background: linear-gradient(92deg, #3e8cf7 0%, #177afa 100%);
        border-radius: 4px 4px 4px 4px;
        font-weight: 500;
        font-size: 13px;

        height: 30px;
        line-height: 30px;
        background: linear-gradient(92deg, #3d3835 0%, #252324 100%);
        border-radius: 15px 15px 15px 15px;
      }
    }
  }
}
</style>
