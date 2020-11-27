<template>
  <view class="news">
    <view class="news-user">
      <!-- 用户信息头 -->
      <view class="user-avatar">
        <u-avatar :src="newsData.src"></u-avatar>
      </view>
      <view class="user-info">
        <span class="info-name">{{ newsData.name }}</span>
        <span class="info-date">{{ newsData.date }}</span>
      </view>
    </view>
    <view class="news-content">
      <!-- 中心内容 -->
      <u-image width="100%" height="500rpx" :src="newsData.imgSrc"></u-image>
    </view>
    <view class="news-info">
      <!-- 动态信息 -->
      <span class="info-title">{{ newsData.title }}</span>
      <u-tag class="info-label" :text="newsData.label" />
    </view>
    <view class="news-handle">
      <!-- 操作 -->
      <view class="handle-btn">
        <u-image
          width="50rpx"
          height="50rpx"
          :fade="false"
          src="/static/icons/share.png"
        ></u-image>
        <span class="handle-name">分享</span>
      </view>

      <view class="handle-btn">
        <u-image
          width="50rpx"
          height="50rpx"
          :fade="false"
          src="/static/icons/comment.png"
        ></u-image>
        <span class="handle-name">{{ newsData.commentNum }}</span>
      </view>
      <view class="handle-btn">
        <u-image
          width="50rpx"
          height="50rpx"
          :fade="false"
          src="/static/icons/like.png"
        ></u-image>
        <span class="handle-name">{{ newsData.likeNum }}</span>
      </view>
    </view>
    <view class="news-comment">
      <!-- 评论 -->
    </view>
  </view>
</template>

<script>
export default {
  data() {
    return {
      newsData: {
        src: '/static/images/user.png',
        name: '雷栋',
        date: '11月26日',
        imgSrc: '',
        title: '本周发售重点关注鞋款一览~各位准备好了吗！',
        label: '球鞋新品曝光',
        commentNum: 11,
        likeNum: 12
      }
    }
  },
}
</script>

<style lang='scss'>
.news {
  display: flex;
  flex-direction: column;

  .news-user {
    display: flex;
    padding: 20px;

    .user-info {
      padding: 5px 10px;
      flex: 1;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      .info-name {
        font-size: 14px;
        font-weight: 600;
      }
      .info-date {
        font-size: 12px;
        color: #b4b3b8;
      }
    }
  }
  .news-info {
    padding: 20px 10px;
    .info-title {
      display: inline-block;
      margin-left: 5px;
      margin-bottom: 10px;
      font-size: 14px;
      font-weight: 600;
    }
    .info-label {
      color: #707176;
      background-color: #f4f5f9;
      border: none;
      font-weight: 600;

      &::before {
        content: "#";
        display: inline-block;
        width: 15px;
        height: 15px;
        line-height: 15px;
        margin-right: 5px;
        color: #ffff;
        text-align: center;
        border-radius: 2px;
        background-color: #616072;
      }
    }
  }
  .news-handle {
    display: flex;
    padding: 0px 15px;
    text-align: center;
    justify-content: space-between;
    .handle-name {
      font-size: 12px;
      color: #878787;
    }
  }
}
</style>