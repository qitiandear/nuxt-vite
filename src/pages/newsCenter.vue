<template>
  <div class="">
    <div class="top">
      <el-image
        :src="newTop"
        style="width: 100%"
        fit="cover"
        class="top-content"
      />
    </div>
    <div style="background: #f2f2f2">
      <div class="new-one">
        <ul class="new-one-left">
          <li
            v-for="item in newList"
            :key="item.id"
            :class="index == item.id ? 'active' : ''"
            @click="change(item.id)"
          >
            <a :href="'#' + item.id"> {{ item.title }}</a>
          </li>
        </ul>
        <div
          style="
            height: 90px;
            line-height: 90px;
            margin-left: 17px;
            margin-right: 15px;
          "
        >
          <el-icon><HomeFilled /></el-icon>
        </div>
        <el-breadcrumb :separator-icon="ArrowRight" class="navigation-bar">
          <el-breadcrumb-item>首页</el-breadcrumb-item>
          <el-breadcrumb-item>新闻中心</el-breadcrumb-item>
          <el-breadcrumb-item>
            <span v-if="index == 1">公司新闻</span>
            <span v-if="index == 2">行业动态</span>
            <span v-if="index == 3">政策法规</span>
          </el-breadcrumb-item>
        </el-breadcrumb>
      </div>
    </div>
    <!-- 公司新闻 -->
    <companyNews id="1" />
    <!-- 行业动态 -->
    <industryDynamic id="2" />
    <!-- 政策法规 -->
    <policiesRegulations id="3" />

    <!-- <el-backtop target=".wraper" :bottom="100" style="width:94px">
      <div
        style="
           {
            height: 100%;
            width: 100%;
            background-color: #f2f5f6;
            box-shadow: 0 0 6px rgba(0, 0, 0, 0.12);
            text-align: center;
            line-height: 40px;
            color: #1989fa;
          }
        "
      >
        返回顶部
      </div>
    </el-backtop> -->
  </div>
</template>
<script setup lang="ts">
import { HomeFilled, ArrowRight } from '@element-plus/icons-vue'
import newTop from '@/assets/images/newTop.png'

const newList = reactive([
  {
    title: '公司新闻',
    id: 1,
  },
  {
    title: '行业动态',
    id: 2,
  },
  {
    title: '政策法规',
    id: 3,
  },
])
const index = ref(1)
const change = (id: number) => {
  index.value = id
}
</script>

<style lang="scss" scoped>
.top {
  height: 500px;
  // width: 1889px;
  .top-content {
    // width: 100%;
    height: 100%;
  }
}
.new-one {
  display: flex;
  height: 90px;
  width: 1440px;
  margin: auto;

  .navigation-bar {
    line-height: 90px;
    // margin-left: 48px;
  }
  .active {
    border-bottom: 2px solid #0087ff;
  }
  .new-one-left {
    display: flex;
    height: 90px;
    width: 70%;
    border-right: 1px solid #d6d6d6;
    line-height: 90px;

    // margin-left: 240px;
    li {
      display: flex;
      align-items: center;
      margin-right: 71px;
    }
  }
}
</style>
