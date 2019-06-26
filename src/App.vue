<template>
  <div class="viewport">
    <!-- 顶部 -->
    <div class="header">
      <span class="logo">传智播客</span>
      <h2>传智播客科技数字可视化平台</h2>
      <span class="title">大数据可视化分析</span>
    </div>
    <!-- 主体部分 -->
    <div class="body">
      <div class="column">
        <!-- 用户 -->
        <div class="panel user">
          <h3>用户实时指标</h3>
        </div>
        <!-- 订单完成率 -->
        <div class="panel channel">
          <h3>订单完成率</h3>
        </div>
        <!-- 转化率分析 -->
        <div class="panel rate">
          <h3>转化率分析</h3>
        </div>
      </div>
      <div class="column">
        <!-- 地图 -->
        <div class="order">
          <div class="caption">
            <span>本月总单: <strong>107</strong> 单</span>
            <span>本月销量: <strong>232</strong> 单</span>
            <h3>今日订单数</h3>
          </div>
        </div>
        <!-- 销量统计 -->
        <div class="sales">
          <!-- 数据 -->
          <div class="data">
            <div class="item">
              <h5>全年金额</h5>
              <span>0</span>
              <span>3</span>
              <span>1</span>
              <span>4</span>
              <span>5</span>
              <span>6</span>
              <span>元</span>
            </div>
            <div class="item">
              <h5>全年销量</h5>
              <span>0</span>
              <span>0</span>
              <span>3</span>
              <span>2</span>
              <span>7</span>
              <span>8</span>
              <span>单</span>
            </div>
          </div>
          <h3>24小时销售统计</h3>
        </div>
      </div>
      <div class="column">
        <!-- 订单状态占比 -->
        <div class="panel status">
          <h3>订单状态占比</h3>
        </div>
        <!-- 订单完成率 -->
        <div class="panel completed">
          <h3>订单完成率</h3>
        </div>
        <!-- 销售趋势 -->
        <div class="panel trend">
          <h3>本周销量趋势</h3>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {

      }
    },
    methods: {
      // 根据视口宽度计算 html 字号大小
      setFont() {
        // 计算浏览器宽度
        let doc = document.documentElement
        let docWidth = doc.clientWidth
        // 限制边界
        if(docWidth < 1024) docWidth = 1024
        if(docWidth > 1920) docWidth = 1920
        // 设置 html 字号大小cons
        doc.style.fontSize = docWidth / 80 + 'px'
      }
    },
    created() {
      // 设置 html 字号
      this.setFont()
      // 根据窗口变化设置 html 定号
      window.addEventListener('resize', () => {
        this.setFont()
      })
    },
    mounted() {

    }
  }
</script>

<style lang="less">
  .viewport {
    min-width: 1024px;
    max-width: 1920px;
    margin: 0 auto;
  }
  
  // 头部
  .header {
    height: 5rem;
    line-height: 1;
    position: relative;

    .logo {
      display: block;
      font-size: 1.125rem;
      color: #c4f7ff;
      position: absolute;
      left: 3rem;
      top: 1rem;
    }

    h2 {
      font-size: 1.333rem;
      color: #c4f7ff;
      transform: translate(-50%);
      position: absolute;
      left: 50%;
      top: 1rem;
    }

    .title {
      display: block;
      font-size: 1rem;
      color: #c4f7ff;
      transform: translate(-50%);
      position: absolute;
      left: 50%;
      bottom: 0.375rem;
    }
  }

  // 主体
  .body {
    display: flex;
    padding: 0.625rem 0.833rem 0;

    // 分成三列
    .column {
      flex: 2;

      &:nth-child(2) {
        flex: 3;
        margin: 0 0.625rem;
      }
    }
    
    // 公共面板
    .panel {
      height: 13.5rem;
      background-image: url(./assets/images/border-1.png);
      background-size: 100% 100%;
      margin-bottom: 1rem;

      h3 {
        height: 1.25rem;
        text-align: center;
        font-size: 0.875rem;
        color: #21fcff;
      }
    }

    // 用户
    .user {

    }

    // 订单来源
    .channel {

    }

    // 转化率
    .rate {

    }

    // 订单数量
    .order {
      height: 20rem;
      padding: 1.7rem 2.5rem 1rem;
      background-image: url(./assets/images/border-2.png);
      background-size: 100% 100%;
      box-sizing: border-box;

      .caption {
        line-height: 1;
        overflow: hidden;
        color: #31ecf0;

        span {
          display: block;
          float: left;
          font-size: 0.75rem;

          &:first-child {
            margin-right: 2.8rem;
          }
        }

        strong {
          font-size: 1rem;
          font-weight: normal;
        }

        h3 {
          float: right;
          font-size: 1rem;
        }
      }
    }

    // 销量统计
    .sales {
      height: 18.5rem;
      background-image: url(./assets/images/border-3.png);
      background-size: 100% 100%;
      margin-top: 4rem;
      padding: 5.5rem 1.5rem 0;
      box-sizing: border-box;
      position: relative;

      h3 {
        font-size: 0.875rem;
        color: #00eaff;
      }

      .data {
        width: 100%;
        height: 6rem;
        position: absolute;
        top: -2.75rem;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
      }

      .item {
        display: flex;
        height: 2rem;
        text-align: center;
        line-height: 2rem;
        margin-left: 4.5rem;
        color: #00e4ff;

        h5 {
          width: 7rem;
          font-size: 0.875rem;
          background-image: url(./assets/images/shape.png);
          background-size: 100% 100%;
        }

        span {
          display: block;
          width: 2rem;
          padding-top: 1px;
          margin: 0 3px;
          font-size: 1.5rem;
          box-sizing: border-box;
          background-image: url(./assets/images/rect.png);
          background-size: 100% 100%;

          &:last-child {
            background-image: none;
            font-size: 1.25rem;
          }
        }
      }
    }

    // 订单状态占比
    .status {

    }

    // 订单完成率
    .completed {

    }

    // 趋势
    .trend {

    }
  }

</style>



