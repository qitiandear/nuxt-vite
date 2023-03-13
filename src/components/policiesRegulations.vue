<template>
  <div class="companyNews">
    <div class="companyNews-top">
      <div style="font-size: 36px">政策法规</div>
      <div style="font-size: 16px">
        查看更多 <el-icon><DArrowRight /></el-icon>
      </div>
    </div>
    <div
      class="companyNews-content-list"
      v-for="(item, index) in newList"
      :key="index"
    >
      <div style="width: 319px; height: 204px">
        <img :src="item.photograph" alt="" style="height: 204px" />
      </div>
      <div style="margin-right: 64px; margin-left: 54px">
        <div style="font-size: 24px; margin-bottom: 24px">{{ item.title }}</div>
        <div style="font-size: 18px">
          {{ item.subtitle }}
        </div>
        <div
          style="
            text-align: right;
            font-size: 18px;
            color: #0087ff;
            margin-top: 25px;
          "
        >
          查看更多<el-icon><DArrowRight /></el-icon>
        </div>
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
</template>
<script setup lang="ts">
import policies1 from '@/assets/images/policies1.png'
import { DArrowRight } from '@element-plus/icons-vue'
import policies2 from '@/assets/images/policies2.png'
import policies3 from '@/assets/images/policies3.png'
const newList = reactive([
  {
    photograph: policies1,
    title: '国务院印发《深化医药卫生体制改革2022年重点工作任务》',
    subtitle:
      '2022年是进入全面建设社会主义现代化国家、向第二个百年奋斗目标进军新征程的重要一年。深化医药卫生体制改革要坚持以习近平新时代中国特色社会主义思想为指导，全面贯彻党的十九大和十九届历次全会精神，认真落实习近平总书记重要指示精神和党中央、国务院决策部署，全面推进...',
    dataTime: '02',
    yearTime: '2022- 05',
  },
  {
    photograph: policies2,
    title: '国家药监局印发关于加强医疗器械跨区域委托生产协同监管工作',
    subtitle:
      '为加强医疗器械注册人备案人跨区域委托生产监管，夯实注册人备案人医疗器械全生命周期质量管理责任，指导地方药品监管部门加强监管工作的协同配合，近日，国家药监局印发《关于加强医疗器械跨区域委托生产协同监管工作的意见》（药监综械管〔2022〕21号）。《意见》包含三个......',
    dataTime: '02',
    yearTime: '2022- 05',
  },
  {
    photograph: policies3,
    title: '全国护理事业发展规划（2021-2025年）',
    subtitle:
      '护理工作是卫生健康事业的重要组成部分，对全面推进健康中国建设、积极应对人口老龄化具有重要意义。为适应人民群众日益增长的健康需求和经济社会发展对护理事业发展的新要求，根据《中华人民共和国国民经济和社会发展第十四个五年规划和2035年远景目标纲要》《“健康中国......',
    dataTime: '02',
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
    align-items: center;
    border-bottom: 1px solid #d7d7d7;
    margin-top: 39px;
    height: 244px;
    .companyNews-content-data {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 154px;
      width: 270px;
      background: url('@/assets/images/bg3.png');
      background-size: cover;
    }
  }
}
</style>
