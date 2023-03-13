<template>
  <div class="footList">
    <div style="display: flex; justify-content: space-between">
      <div class="footTop">
        <dl
          v-for="(item, index) in list"
          :key="index"
          style="margin-right: 70px; margin-top: 0"
        >
          <dt style="font-size: 22px; color: #ffffff; margin-bottom: 30px">
            {{ item.title }}
          </dt>
          <dd
            v-for="(temp, index) in item.contentList"
            :key="index"
            style="font-size: 18px; color: #999999; margin: auto"
          >
            {{ temp.name }}
          </dd>
        </dl>
      </div>
      <div style="display: flex; align-items: center">
        <div>
          <div
            style="display: flex"
            v-for="(item, index) in contact"
            :key="index"
          >
            <el-image :src="item.img" alt="" class="foot-top-picture" />
            <div style="font-size: 18px; color: #ffffff">{{ item.title }}</div>
          </div>
        </div>
        <div style="" class="line"></div>
        <div>
          <div style="width: 106px; height: 106px">二维码</div>
          <div>扫一扫关注我们</div>
        </div>
      </div>
    </div>
    <div
      style="
        display: flex;
        justify-content: space-between;
        color: #999999;
        margin-top: 93px;
      "
    >
      <div style="font-size: 16px">
        Copyright 2015-2020 杏林丹心 - powered By XLDX V1.0.0 晋ICP备 16000872
        号
      </div>
      <div>
        <ul style="display: flex; font-size: 18px">
          <li style="margin-right: 60px">隐私条款</li>
          <li style="margin-right: 60px">加入我们</li>
          <li>联系我们</li>
        </ul>
      </div>
    </div>
  </div>
</template>
<script setup lang="ts">
const list = reactive([
  {
    title: '关于我们',
    contentList: [
      {
        name: '公司简介',
      },
      {
        name: '组织架构',
      },
      {
        name: '品牌经典',
      },
    ],
  },
  {
    title: '服务对象',
    contentList: [
      {
        name: '生产厂家',
      },
      {
        name: '发货平台',
      },
      {
        name: '客户',
      },
    ],
  },
  {
    title: '产品优势',
    contentList: [
      {
        name: '智慧科技',
      },
      {
        name: '规范管理',
      },
      {
        name: '优质服务',
      },
    ],
  },
  {
    title: '最新动态',
    contentList: [
      {
        name: '公司新闻',
      },
      {
        name: '行业动态',
      },
      {
        name: '政策法规',
      },
    ],
  },
  {
    title: '社会责任',
    contentList: [
      {
        name: '公益事件',
      },
      {
        name: '加入我们',
      },
    ],
  },
])
const contact = reactive([
  {
    img: new URL('@/assets/images/phone.png', import.meta.url).href,
    title: '0351- 8786003',
  },
  {
    img: new URL('@/assets/images/webaddress.png', import.meta.url).href,
    title: 'www.xldxchina.com',
  },
  {
    img: new URL('@/assets/images/mail.png', import.meta.url).href,
    title: 'xldxchina@163.com',
  },
  {
    img: new URL('@/assets/images/fax.png', import.meta.url).href,
    title: '0351- 8786003',
  },
])
</script>

<style lang="scss" scoped>
.footList {
  color: #ffffff;
  // margin-top: 55px;
  padding: 120px 228px 177px 220px;
  box-sizing: border-box;
  height: 540px;
  background: #3b3b3b;

  .footTop {
    display: flex;
  }

  .foot-top-picture {
    width: 28px;
    margin-right: 20px;
    margin-bottom: 15px;
  }

  .line {
    width: 1px;
    height: 120px;
    background: #ffffff;
    opacity: 0.33;
    margin: 0 35px;
  }
}
</style>
