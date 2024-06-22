<template>
  <view class="content">
    <!-- <u-navbar
      class="nav-bar"
      placeholder
      @rightClick="rightClick"
      leftIcon=""
      bgColor="rgba(0,0,0,0)"
      :style="{ height: navHeight + 'px' }"
    >
      <u-search
        slot="center"
        shape="round"
        placeholder="请输入关键字"
      ></u-search>
    </u-navbar> -->

    <NavBar></NavBar>
    <view class="swiper-wrap">
      <u-swiper :list="list1" @change="change" @click="click"></u-swiper>
    </view>

    <view class="grid-wrap">
      <u-grid :border="false" @click="clickGrid">
        <u-grid-item
          v-for="(baseListItem, baseListIndex) in baseList"
          :key="baseListIndex"
        >
          <u-icon
            :customStyle="{ marginBottom: 4 + 'rpx' }"
            :name="baseListItem.name"
            :size="38"
          ></u-icon>
          <text class="{ }">{{ baseListItem.title }}</text>
        </u-grid-item>
      </u-grid>
    </view>

    <view class="grid-wrap grid-wrap-1">
      <u-grid :border="false" @click="clickGrid" col="5">
        <u-grid-item
          v-for="(baseListItem, baseListIndex) in baseList1"
          :key="baseListIndex"
          :class="{
            'grid-wrap-1__bot': baseListIndex > 4,
          }"
        >
          <u-icon
            :customStyle="{ marginBottom: 4 + 'rpx' }"
            :name="baseListItem.name"
            :size="28"
          ></u-icon>
          <text class="{ }">{{ baseListItem.title }}</text>
        </u-grid-item>
      </u-grid>
    </view>

    <view class="sec-tit">
      <text class="left"> 热门课程 </text>
      <view class="right">
        <text style="margin-right: 4rpx"> 查看更多 </text>
        <u-icon name="arrow-right" :size="10"></u-icon>
      </view>
    </view>

    <CourseCard v-for="item in courses" :key="index" :item="item"> </CourseCard>
    <!-- <image class="logo" src="@/static/logo.png"></image>
    <view class="text-area">
      <text class="title">Hello RuoYi</text>
    </view> -->
  </view>
</template>

<script>
export default {
  data() {
    return {
      navHeight: "",
      customTop: "",
      customHeight: "",
      list1: [require("./../static/images/banner/banner01.png")],
      baseList: [
        {
          name: require("./../static/images/grid/grid0.png"),
          title: "查故障码",
        },
        {
          name: "lock",
          name: require("./../static/images/grid/grid1.png"),
          title: "KP定义",
        },
        {
          name: "star",
          name: require("./../static/images/grid/grid2.png"),
          title: "ECU定义",
        },
      ],
      baseList1: [
        {
          name: require("./../static/images/grid/grid00.png"),
          title: "☹️故障码",
        },
        {
          name: "lock",
          name: require("./../static/images/grid/grid01.png"),
          title: "查仪表灯",
        },
        {
          name: "star",
          name: require("./../static/images/grid/grid02.png"),
          title: "查线号",
        },
        {
          name: "star",
          name: require("./../static/images/grid/grid03.png"),
          title: "部件信息",
        },
        {
          name: "star",
          name: require("./../static/images/grid/grid04.png"),
          title: "整车资料",
        },

        {
          name: "star",
          name: require("./../static/images/grid/grid05.png"),
          title: "ECU定义",
        },
        {
          name: "star",
          name: require("./../static/images/grid/grid06.png"),
          title: "DCU定义",
        },

        {
          name: "star",
          name: require("./../static/images/grid/grid07.png"),
          title: "车身模块",
        },

        {
          name: "star",
          name: require("./../static/images/grid/grid08.png"),
          title: "仪表模块",
        },
        {
          name: "star",
          name: require("./../static/images/grid/grid09.png"),
          title: "门窗模块",
        },
      ],
      courses: [
        {
          cover: "",
          name: "康明斯专检诊断",
          time: "发布时间 2024年06月12日",
          tag: ["免费"],
          views: 1135,
        },
        {
          cover: "",
          name: "4缸冷启动修改方法",
          time: "发布时间 2024年06月12日",
          tag: ["免费"],
          views: 1035,
        },
      ],
    };
  },
  methods: {
    change() {},
    click() {},
    clickGrid(name) {},
  },
  onLoad() {
    let custom = uni.getMenuButtonBoundingClientRect(); // 小程序右上角胶囊信息
    let system = uni.getSystemInfoSync(); // 获取设备信息
    this.navHeight = system.statusBarHeight + 44; // 导航栏的高度
    this.customTop = custom.top; // 胶囊按钮与顶部的距离
    this.customHeight = custom.height; // 胶囊按钮与右侧的距离
  },
};
</script>

<style>
page {
  background: linear-gradient(180deg, #d4e8fd 0%, rgba(255, 255, 255, 0) 100%)
    no-repeat #f8f9fc;
  background-size: 100% 140px;
}
</style>

<style lang="scss" scoped>
.nav-bar {
  width: 70% !important;
}

/deep/ .u-search__content {
  width: 100% !important;
}

.content {
  padding: 0 16px 16px 16px;
  min-height: 100vh;
}

.top-bg {
  /* background: linear-gradient(180deg, #d4e8fd 0%, rgba(255, 255, 255, 0) 100%); */
  padding: 0 16px 16px 16px;
}

.swiper-wrap {
  margin-top: 12px;
  margin-bottom: 10px;
}

.grid-wrap {
  border-radius: 8px 8px 8px 8px;
  background: #fff;
  padding: 14px 0;
  margin-bottom: 10px;

  .grid-text {
    font-weight: 400;
    font-size: 22rpx;
    color: #333333;
  }
}

.grid-wrap-1 {
  padding-top: 0;
  /* border-radius: 8px 8px 8px 8px;
  background: #fff;
  padding: 14px 0;
  margin-bottom: 10px; */

  // .u-grid-item:nth-child(6),
  // .u-grid-item:nth-child(7),
  // .u-grid-item:nth-child(8),
  // .u-grid-item:nth-child(9),
  // .u-grid-item:nth-child(10) {
  //   margin-top: 20px;
  // }

  // &__bot {
    /deep/ .u-grid-item {
      margin-top: 20px;
    }
  // }
}

.sec-tit {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 10px;

  .left {
    font-weight: bold;
    font-size: 14px;
    color: #131d34;
    flex: 1;
    padding-left: 10px;
    position: relative;

    &::before {
      position: absolute;
      content: "";
      width: 3px;
      height: 14px;
      background: #177afa;
      border-radius: 2px 2px 2px 2px;
      left: 0px;
      top: 50%;
      transform: translateY(-50%);
    }
  }

  .right {
    font-weight: 500;
    font-size: 12px;
    color: #818ca4;
    display: flex;
    align-items: center;
  }
}

.logo {
  margin-left: auto;
  margin-right: auto;
  margin-top: 200rpx;
  margin-bottom: 50rpx;
  width: 200rpx;
  height: 200rpx;
}

.text-area {
  display: flex;
  justify-content: center;
}

.title {
  font-size: 36rpx;
  color: #8f8f94;
}

.uni-margin-wrap {
  width: 690rpx;
  width: 100%;
}
.swiper {
  height: 300rpx;
}
.swiper-item {
  display: block;
  height: 300rpx;
  line-height: 300rpx;
  text-align: center;
}
.swiper-list {
  margin-top: 40rpx;
  margin-bottom: 0;
}
.uni-common-mt {
  position: relative;
  margin-top: 60rpx;
}
.info {
  position: absolute;
  right: 20rpx;
}
.uni-padding-wrap {
  padding: 0 100rpx;
  width: 550rpx;
}
</style>
