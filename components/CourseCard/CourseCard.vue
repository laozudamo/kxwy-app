<template>
  <view class="card">
    <view class="cover"> </view>
    <view class="info">
      <view class="top">
        {{ item.name }}
      </view>
      <view class="time">
        {{ item.time }}
      </view>

      <view class="tag" v-for="el in item.tag" :key="el">
        {{ el }}
      </view>
      <view class="bot">
        <view class="view">
          {{ item.views }}
        </view>
        <button class="btn">查看</button>
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
  margin-bottom: 8px;
  .cover {
    width: 125px;
    height: 96px;
    background: #000000;
    border-radius: 8px 8px 8px 8px;
    opacity: 0.4;
  }
  .info {
    margin-left: 11px;
    flex: 1;
    display: flex;
    flex-direction: column;
    justify-content: space-between;

    .top {
      font-weight: 500;
      font-size: 13px;
      color: #131d34;
      margin-bottom: 6px;
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
        line-height: 26px;
        color: #fff;
        width: fit-content;
        background: linear-gradient(92deg, #3e8cf7 0%, #177afa 100%);
        border-radius: 4px 4px 4px 4px;
        font-weight: 500;
        font-size: 13px;
      }
    }
  }
}
</style>
