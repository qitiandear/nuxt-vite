<template>
  <div class="home">
    <div class="OMS-top">
      <!-- <div style="font-size: 60px; margin-bottom: 10px">
        骨科智能物流管理系统
      </div>
      <div style="font-size: 16px">
        实现了从物流决策、业务流程、客户服务的全程信息化，对物流进行科学管理。由人员、<br />计算机硬件、软件、网络通信设备及其它办公设备组成的人机交互系统，其主要功能是<br />
        进行物流信息的收集、存储、传输、加工整理、维护和输出，为物流管理者及其它组织<br />管理人员提供战略、战术及运作决策的支持，以达到组织的战略竞优，提高物流运作的<br />效率与效益。
      </div> -->
    </div>
    <navigationBar @change="change" />
    <div
      id="1"
      style="margin: 98px 278px; display: flex; justify-content: space-between"
    >
      <div class="OMS-one" v-for="item in list" :key="item.id">
        <img :src="item.pic" alt="" class="OMS-image" />
        <div>{{ item.title }}</div>
        <!-- <div>{{ item.name }}</div> -->
      </div>
    </div>
    <productValue id="2" />
    <productSuperiority :list="advantageList" id="3" />
    <div
      style="
        width: 1440px;
        margin: auto;
        margin-bottom: 188px;
        margin-top: 78px;
      "
      id="4"
    >
      <img
        src="@/assets/images/OMS01/bottompng.png"
        alt=""
        style="width: 100%"
      />
    </div>
  </div>
</template>
<script setup lang="ts">
const advantageList = reactive([
  {
    titleHidden: true,
    id: 1,
    place: 'left',
    pic: new URL('@/assets/images/cases/ztsa1.png', import.meta.url).href,
    title: '实现了全院业务流程的通畅和信息资源的共享',
    content: `1、以患者为中心，完成患者病历文档的读写、传输、存储和调用，医院医护人员可以方便的查看和调阅这些文档，实现了全院业务流程的通畅和信息资源的共享；<br />2、医生可以在一个集成界面中方便的查看当前病人的这种检验、检查数据，当前的病历、病程记录、护理记录、体温单、医嘱信息等；<br />3、采用专业电子病历编辑器，完全符合Office操作习惯，录入内容所见即所得，符合医生书写病历的习惯，培训简单；<br />4、基于XML结构化储存，提供病历的全文的检索，统计功能；`,
  },
  {
    id: 2,
    place: 'right',
    pic: new URL('@/assets/images/cases/ztsa2.png', import.meta.url).href,
    title: '提供完善的病历模板管理机制',
    content:
      '1、提供完善的病历模板管理机制，实现医生自行维护模板;病历书写支持文字、类似Word、EXCEL表格、图形、图像等多种方式，可对文字、表格、图形、图像等进行再编辑，医生可以对模板中的元素可以自行设定是否可以删除、必选；<br />2、结构化电子病历读写、传输、存储和调用功能;支持后续临床路径的应用；<br />3、有动态权限设置功能，可以基于病历段落设置不同的书写、修改权限；',
  },
  {
    id: 3,
    place: 'left',
    pic: new URL('@/assets/images/cases/ztsa4.png', import.meta.url).href,
    title: '完备的功能和完善的机制',
    content:
      '1、病历集中打印、续打、分页打印等功能；支持病历自动排版功能，提供打印功能；2、医生可以查看患者各种护理记录；<br />3、提供医生常用医学符号，体征，症状，常用词，各种字典、常用计算公式等;<br />4、医生可以方便的查看患者历次的住院的就诊记录各种诊疗数据，并能方便的引用到本次就诊中；<br />5、通过系统中的消息平台，实现医护工作站之间的消息交互，医护工作站与质控科质控信息交互；<br />6、实现单一权限书写，多人查看机制；',
  },
  {
    id: 4,
    place: 'right',
    pic: new URL('@/assets/images/cases/ztsa5.png', import.meta.url).href,
    title: '实现了全院业务流程的通畅和信息资源的共享',
    content:
      '1、提供完善的病历模板管理机制，实现医生自行维护模板;病历书写支持文字、类似Word、EXCEL表格、图形、图像等多种方式，可对文字、表格、图形、图像等进行再编辑，医生可以对模板中的元素可以自行设定是否可以删除、必选；<br />2、结构化电子病历读写、传输、存储和调用功能;支持后续临床路径的应用；<br />3、有动态权限设置功能，可以基于病历段落设置不同的书写、修改权限；',
  },
])
const list = reactive([
  {
    id: 1,
    pic: new URL('@/assets/images/cases/pic1.png', import.meta.url).href,
    title: '严格遵循标准',
  },
  {
    id: 2,
    pic: new URL('@/assets/images/cases/pic2.png', import.meta.url).href,
    title: '结构化',
  },
  {
    id: 3,
    pic: new URL('@/assets/images/cases/pic3.png', import.meta.url).href,
    title: '区域化',
  },
  {
    id: 4,
    pic: new URL('@/assets/images/cases/pic4.png', import.meta.url).href,
    title: '高度自定义',
  },
])
const index = ref<number>()
const change = (id: number) => {
  index.value = id
}
</script>
<style lang="scss" scoped>
.OMS-top {
  height: 500px;
  background: url('@/assets/images/cases/banner.png');
  background-size: cover;
  color: #ffffff;
  box-sizing: border-box;
  padding-top: 135px;
  padding-left: 291px;
}
.OMS-one {
  font-size: 26px;
  color: #333333;
  width: 163px;
  text-align: center;
  .OMS-image {
    width: 100%;
    margin-bottom: 40px;
  }
}
</style>
