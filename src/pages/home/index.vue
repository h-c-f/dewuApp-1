<template>
  <view class="home">
    <view class="home-header">
      <u-navbar :is-back="false" class="home-navbar">
        <view class="slot-left">
          <u-icon name="search" class="navbar-icon"></u-icon>
        </view>
        <view class="slot-wrap">
          <u-tabs
            ref="tabs"
            :is-scroll="false"
            :show-bar="false"
            :list="tabList"
            :current="current"
            class="home-tabs"
            @change="tabsChange"
            inactive-color="#aeadb3"
            active-color="#0d0d0d"
          ></u-tabs>
        </view>
        <view class="slot-rghit">
          <u-icon name="camera-fill" class="navbar-icon"></u-icon>
        </view>
      </u-navbar>
    </view>
    <view class="home-content">
      <template v-for="(item, index) in newsList">
        <dewu-news :key="index"></dewu-news>
      </template>
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      tabList: [
        { name: '关注' },
        { name: '推荐' },
        { name: 'LIVE' },
      ],
      current: 0,
      newsList:[
        {},
        {},
        {},
        {},
      ]
    }
  },
  methods: {
    tabsChange(index) {
      // 选项卡点击事件
      this.current = index;

    }
  },
}
</script>

<style lang="scss">
.home {
  .home-header {
    .home-navbar {
      /deep/ .u-navbar-fixed {
        padding: 0 20px;
      }
      .navbar-icon {
        font-size: 20px;
        color: #030303;
      }
      .slot-wrap {
        padding: 0 60px;
        display: flex;
        flex: 1;
        .home-tabs {
          flex: 1;
        }
      }
    }
  }
  .home-content {
  }
}
</style>