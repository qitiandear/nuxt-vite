<template>
  <div class="companyNews">
    <div class="companyNews-top">
      <div style="font-size: 36px">公司新闻</div>
      <div style="font-size: 16px">
        查看更多 <el-icon><DArrowRight /></el-icon>
      </div>
    </div>
    <div class="companyNews-content-list">
      <div
        class="companyNews-content"
        v-for="(item, index) in newList"
        :key="index"
      >
        <div class="companyNews-picture">
          <img :src="item.picture" alt="" style="width: 100%" />
        </div>
        <div class="companyNews-content-bottom">
          <div>{{ item.title }}</div>
          <div class="companyNews-content-data">
            <div style="font-size: 35px; color: #0087ff">
              {{ item.dataTime }}
            </div>
            <div style="font-size: 14px; color: #666666">
              {{ item.yearTime }}
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script setup lang="ts">
import { DArrowRight } from '@element-plus/icons-vue'
import news1 from '@/assets/images/news1.png'
import news2 from '@/assets/images/news2.png'
import news3 from '@/assets/images/news3.png'
const newList = reactive([
  {
    picture: news1,
    title: '公司员工志愿者全力以赴服务社区疫情防疫工作',
    dataTime: '02',
    yearTime: '2022- 05',
  },
  {
    picture: news2,
    title: '公司员工志愿者全力以赴服务社区疫情防疫工作',
    dataTime: '13',
    yearTime: '2022- 04',
  },
  {
    picture: news3,
    title: '2022年4月13日，我司为某部成功组建跟台团队',
    dataTime: '24',
    yearTime: '2021- 09',
  },
  {
    picture: news1,
    title: '2021年9月24日，为提升团队凝聚力，公司组织了全员团建活动',
    dataTime: '02',
    yearTime: '2022- 05',
  },
  {
    picture: news2,
    title: '公司员工志愿者全力以赴服务社区疫情防疫工作',
    dataTime: '13',
    yearTime: '2022- 04',
  },
  {
    picture: news3,
    title: '2022年4月13日，我司为某部成功组建跟台团队',
    dataTime: '24',
    yearTime: '2021- 09',
  },
])
</script>
<style lang="scss" scoped>
img {
  padding: 0;
  margin: 0;
}
.companyNews {
  margin: auto;
  width: 1440px;
  color: #333333;
  .companyNews-top {
    display: flex;
    justify-content: space-between;
    align-items: baseline;
    margin-top: 59px;
  }
  .companyNews-content-list {
    display: flex;
    flex-wrap: wrap;
    > :nth-child(3n) {
      margin-right: 0;
    }
  }
  .companyNews-content {
    margin-top: 59px;
    width: 456px;
    margin-right: 35px;
    .companyNews-picture {
      width: 456px;
      height: 257px;
      padding: 0;
      margin: 0;
    }
    .companyNews-content-bottom {
      display: flex;
      align-items: center;
      width: 457px;
      height: 102px;
      box-sizing: border-box;
      background: #ffffff;
      padding-right: 29px;
      padding-left: 42px;
      border: 1px solid #e1e1e1;
      .companyNews-content-data {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        height: 72px;
        width: 92px;
        background: url('@/assets/images/bg.png');
        background-size: cover;
      }

      // border-top: 0px;
    }
  }
}
</style>
