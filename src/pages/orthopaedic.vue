<template>
  <div class="home">
    <div class="OMS-top">
      <div style="font-size: 60px; margin-bottom: 10px">
        骨科智能物流管理系统
      </div>
      <div style="font-size: 16px">
        实现了从物流决策、业务流程、客户服务的全程信息化，对物流进行科学管理。由人员<br />
        计算机硬件、软件、网络通信设备及其它办公设备组成的人机交互系统，其主要功能是<br />
        进行物流信息的收集、存储、传输、加工整理、维护和输出，为物流管理者及其它组织<br />
        管理人员提供战略、战术及运作决策的支持，以达到组织的战略竞优，提高物流运作的<br />
        效率与效益。
      </div>
    </div>
    <navigationBar @change="change" />
    <productValue id="3" />
    <div
      style="
        width: 1440px;
        margin: auto;
        margin-bottom: 188px;
        margin-top: 50px;
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
const list = reactive([
  {
    id: '1',
    pic: new URL('@/assets/images/orthopaedic/cn2.png', import.meta.url).href,
    title: '通过自动化、协同化、智能化减少人工操作',
    content:
      '运输管理云能够帮助生产厂家、供应商、经销商及医院通过PC端或手机端访问同一个共享的云 平台，实现物流工作协同化及流程360度可视化，解决方案能够从多场景、自动化、实时可控多 个维度满足物流管理需求，实现物流资源整合、物流部门进行运输资源整合、智能计划调度、物 流可视化、物流可控化、物流费用智能结算以及数据智能分析。',
  },
  {
    id: '2',
    pic: new URL('@/assets/images/orthopaedic/cn2-cdn.png', import.meta.url)
      .href,
    title: '智慧物流赋能运输配送',
    content:
      '在医疗行业的配送利润日益微薄的压力下，杏林丹心通过基于智能算法的配送装车计划和配送 路线优化，实现降本增效。为客户构建基于AI及运筹优化的智能决策平台，利用运输能力，提 高运输效率；以最小的运输劳动耗费，及时满足运输需要，使货物走最合理的路线来取得较好 经济效益。我们将快速为客户开发和部署通用化和定制化的智能决策产品，在车辆路径优化、 装箱优化、库存及网络优化、需求预测优化等供应链场景中，研发并落地AI产品及服务，为客 户提供更加智能的供应链产品及服务。',
  },
  {
    id: '3',
    pic: new URL('@/assets/images/orthopaedic/cn2-ddos.png', import.meta.url)
      .href,
    title: '支撑面向多渠道业务的服务能力',
    content:
      '协同端的供应商、生产厂家、经销商、承运商、司机、医院，可以在平台上作快速的共享和连接；基于供应链执行的数据，做供应链计划，包含需求优化、网络优化、需求预测、库存网络预测、运输优化等等。满足第三方物流的多重要求：支撑面向多渠道业务的服务能力、多货主管理、药监安全合规、库存协同管控、全国服务网络、支持面向终端的配送、信息化对接、全程可视化、可追溯管理等等。',
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
  background: url('@/assets/images/orthopaedic/light.png');
  background-size: cover;
  color: #ffffff;
  box-sizing: border-box;
  padding-top: 135px;
  padding-left: 291px;
}
</style>
