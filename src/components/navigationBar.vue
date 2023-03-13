<template>
  <div style="background: #f2f2f2">
    <div class="new-one">
      <ul class="new-one-left">
        <li
          v-for="item in newList"
          :key="item.id"
          :class="index == item.id ? 'active' : ''"
          @click="change(item.id)"
        >
          <a :href="'#' + item.id">{{ item.title }}</a>
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
          <span v-if="index == 1">产品优势</span>
          <span v-if="index == 2">产品应用价值</span>
          <span v-if="index == 3">产品功能</span>
          <span v-if="index == 4">免费试用</span>
        </el-breadcrumb-item>
      </el-breadcrumb>
    </div>
  </div>
</template>
<script setup lang="ts">
import { HomeFilled, ArrowRight } from '@element-plus/icons-vue'

interface product {
  title?: string
  id?: number
}
interface proList {
  newList: product[]
}
withDefaults(defineProps<proList>(), {
  newList: () => [
    { title: '产品优势', id: 1 },
    { title: '产品应用价值', id: 2 },
    { title: '产品功能', id: 3 },
    { title: '免费试用', id: 4 },
  ],
})
const emit = defineEmits(['change'])
const index = ref(1)
const change = (id?: number) => {
  index.value = id ? id : 1
  emit('change', id)
}
</script>
<style lang="scss" scoped>
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
