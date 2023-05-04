// 在宽度小于等于 576px 的屏幕上，
// 将 html 元素的字体大小设置为 13.3333vw。

// vw 单位指的是视窗宽度的百分比，例如 1vw 
// 代表视窗宽度的 1%。因此，当 font-size 设置
// 为 13.3333vw 时，它的大小将根据窗口宽度自动缩放。

// 使用这种方法可以很好地解决移动设备屏幕大小不同的问
// 题。一旦窗口宽度小于等于 576px，字体大小将自动适应
// ，并使页面更易于阅读和导航。此外，它还可以确保更
// 好的用户体验和可访问性。

<template>
  <div id="app">
    <p>12345</p>
    <div class="color-block red">123456</div>
    <div class="color-block yellow">455666</div>
    <div class="color-block blue">ggggg</div>
    <van-button type="primary" @click="handclicktwo">主要按钮</van-button>
    <button @touchstart="handclicktwo" @touchmove="handmoveone" @touchend="handend">test</button>
    <van-button type="success">成功按钮</van-button>
    <van-button type="default">默认按钮</van-button>
    <van-button type="warning">警告按钮</van-button>
    <van-button type="danger">危险按钮</van-button>
    <van-cell-group>
      <van-cell title="单元格" value="内容" />
      <van-cell title="单元格" value="内容" label="描述信息" />
    </van-cell-group>
  </div>
</template>

<script>

export default {
  data() {
    return {
      touchstarttime: "0"
    };
  },
  name: "App",
  components: {},
  methods: {
    handclickone(e) {
      console.log(e, "1");
    },
    handclicktwo(e) {
      //获取当前日期的时间戳
      this.touchstarttime = new Date().getMilliseconds();
      console.log(e, "2");
    },
    handmoveone(e) {
      console.log(e, "3");
    },
    handend(e) {
      this.touchstarttime = new Date().getMilliseconds() - this.touchstarttime;
      console.log(e, "4", this.touchstarttime);
      if (this.touchstarttime > 300) {
        alert("长按触发");
      }
    }
  }
};
</script>

<style scoped>
/* html {
  font-size: 16px;
} */
.color-block {
  width: 30%;
  margin: 5%;
  padding: 20% 0;
  display: inline-block;
  text-align: center;
  font-size: 16px;
  font-weight: bold;
  border-radius: 50px;
  box-shadow: 1px 1px 10px rgba(128, 128, 128, 0.4);
}
.red {
  background-color: #ff4e4e;
}
.yellow {
  background-color: #fece44;
}
.blue {
  background-color: #44b2fe;
}

@media screen and (max-width: 576px) {
  .color-block {
    font-size: 30px;
    height: 50px;
    background-color: aqua;
  }
}

/* 不同背景色 */

</style>
