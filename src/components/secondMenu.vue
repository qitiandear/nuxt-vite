<template>
  <div class="second_menu_box">
    <div class="s_menu_cont">
      <ul class="menu_l">
        <li
          v-for="(item, index) in littleMenu"
          :key="index"
          :class="{ active: activeMenu == String(item.id) }"
          @click="clickMenu(item)"
        >
          <a :href="'#' + item.id">{{ item.title }}</a>
        </li>
      </ul>
      <div class="menu_r">
        <el-breadcrumb :separator-icon="ArrowRight" class="navigation-bar">
          <el-breadcrumb-item>
            <el-icon><HomeFilled /></el-icon
            ><span style="padding: 0 0 0 20px">首页</span>
          </el-breadcrumb-item>
          <el-breadcrumb-item>新闻中心</el-breadcrumb-item>
        </el-breadcrumb>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { HomeFilled, ArrowRight } from '@element-plus/icons-vue'
interface news {
  title: string
  id: number
}
interface Props {
  littleMenu: news[]
}

const props = defineProps<Props>()

const activeMenu = ref('')

const emit = defineEmits(['clickSecondMenu'])

const clickMenu = (item: news) => {
  activeMenu.value = String(item.id)
  emit('clickSecondMenu', item)
}

onMounted(() => {
  activeMenu.value = props.littleMenu[0] ? String(props.littleMenu[0].id) : ''
})
</script>
<style lang="scss" scoped>
.second_menu_box {
  background: #f4f1f4;

  .s_menu_cont {
    display: flex;
    height: 90px;
    width: 1440px;
    margin: 0 auto;

    .navigation-bar {
      line-height: 90px;
    }
    .active {
      border-bottom: 2px solid #0087ff;
    }
    .menu_l {
      display: flex;
      height: 90px;
      width: 70%;
      border-right: 1px solid #d6d6d6;
      line-height: 90px;
      li {
        display: flex;
        align-items: center;
        margin-right: 50px;
        padding: 0 30px;
        font-size: 24px;
        &:hover {
          cursor: pointer;
        }
      }
    }
    .menu_r {
      height: 90px;
      line-height: 90px;
      margin-left: 17px;
      margin-right: 15px;
      .el-breadcrumb__inner {
        font-size: 16px;
      }
      .el-icon-s-home {
        margin: 0 15px;
      }
    }
  }
}
</style>
