<template>
  <div class="companyNews">
    <div class="companyNews-top">
      <div style="font-size: 36px">行业动态</div>
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
        <div style="margin-right: 35px">
          <div
            style="
              font-size: 18px;
              color: #666666;
              font-weight: 700;
              margin-bottom: 16px;
            "
          >
            {{ item.titel }}
          </div>
          <div style="font-size: 16px; color: #666666">{{ item.subtitle }}</div>
        </div>
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
</template>
<script setup lang="ts">
import { DArrowRight } from '@element-plus/icons-vue'

const newList = reactive([
  {
    titel: '卫计委“放管服”改革，推出十项重点改革举措',
    subtitle:
      '国家卫生计生委8月10日例行新闻发布会文字实录摘要   时间：2017年８月10日 地点：西直门办公区2号楼1层新闻发布厅...',
    dataTime: '24',
    yearTime: '2021- 09',
  },
  {
    titel: '18家国产械企产品被踢出江西省招标',
    subtitle:
      '医用耗材最低价格申报，又一省出手了！7月31日，江西省医药采购服务中心发布了《关于公布医用耗材集中挂网采购有关申投诉...',
    dataTime: '17',
    yearTime: '2022- 05',
  },
  {
    titel: '卫计委“放管服”改革，推出十项重点改革举措',
    subtitle:
      '国家卫生计生委8月10日例行新闻发布会文字实录摘要   时间：2017年８月10日 地点：西直门办公区2号楼1层新闻发布厅...',
    dataTime: '04',
    yearTime: '2021- 09',
  },
  {
    titel: '18家国产械企产品被踢出江西省招标',
    subtitle:
      '医用耗材最低价格申报，又一省出手了！7月31日，江西省医药采购服务中心发布了《关于公布医用耗材集中挂网采购有关申投诉...',
    dataTime: '17',
    yearTime: '2022- 05',
  },
  {
    titel: '卫计委“放管服”改革，推出十项重点改革举措',
    subtitle:
      '国家卫生计生委8月10日例行新闻发布会文字实录摘要   时间：2017年８月10日 地点：西直门办公区2号楼1层新闻发布厅...',
    dataTime: '19',
    yearTime: '2021- 09',
  },
  {
    titel: '18家国产械企产品被踢出江西省招标',
    subtitle:
      '医用耗材最低价格申报，又一省出手了！7月31日，江西省医药采购服务中心发布了《关于公布医用耗材集中挂网采购有关申投诉...',
    dataTime: '17',
    yearTime: '2022- 05',
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
    > :nth-child(2n) {
      margin-right: 0;
    }
  }
  .companyNews-content {
    margin-top: 29px;
    display: flex;
    align-items: center;
    padding-left: 30px;
    padding-right: 20px;
    width: 700px;
    height: 135px;
    box-sizing: border-box;
    margin-right: 35px;
    border: 1px solid #d5d5d5;

    &:hover {
      border: 0;
      box-shadow: 0px 1px 14px 0px rgba(0, 84, 159, 0.34);
    }
    .companyNews-content-data {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 99px;
      width: 139px;
      background: url('@/assets/images/bg.png');
      background-size: cover;
    }
  }
}
</style>
