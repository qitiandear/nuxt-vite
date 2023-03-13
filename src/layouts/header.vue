<template>
  <div class="top">
    <img src="@/assets/images/logo.png" alt="" />
    <ul style="height: 100%">
      <li
        v-for="item in directoryList"
        :key="item.id"
        style="
          margin-right: 80px;
          display: flex;
          align-items: center;
          cursor: pointer;
        "
        @click="change(item.id, item.jump)"
        :class="item.id == selectedTab ? 'active' : ''"
        @mouseover="enter(item.id)"
        @mouseout="leave(item.id)"
      >
        <div>{{ item.name }}</div>
        <!-- :class="productList== 2 ? 'sub-content' : ''" -->
      </li>
    </ul>

    <el-button :icon="Search" circle />
    <div
      class="sub-content"
      v-show="contentShow"
      @mouseout="contentShow = false"
      @mouseover="contentShow = true"
    >
      <dl
        v-for="(item, index) in list"
        :key="index"
        style="margin-right: 70px; margin-top: 0"
      >
        <dt
          style="
            font-size: 20px;
            color: #ffffff;
            margin-bottom: 30px;
            height: 30px;
          "
        >
          {{ item.title }}
        </dt>
        <dd
          v-for="(temp, index) in item.contentList"
          :key="index"
          @click="routingHop(temp.jump)"
          class="passDD"
        >
          {{ temp.name }}
        </dd>
      </dl>
    </div>
  </div>
</template>
<script setup lang="ts">
import { useRouter } from 'vue-router'
import { Search } from '@element-plus/icons-vue'

const router = useRouter()
const emit = defineEmits(['switchNavigation'])
const selectedTab = ref(1)
const contentShow = ref(false)
const index = ref(1)
const productList = ref(1)
const directoryList = reactive([
  {
    id: 1,
    name: '首页',
    jump: '',
  },
  {
    id: 2,
    name: '产品介绍',
    jump: 'introduce',
  },
  {
    id: 3,
    name: '新闻中心',
    jump: 'newsCenter',
  },
  {
    id: 4,
    name: '合作伙伴',
    jump: 'cooperation',
    //  jump: "beingDeveloped"
  },
  {
    id: 5,
    name: '管理平台',
    jump: 'management',
  },
  {
    id: 6,
    name: '关于我们',
    jump: 'aboustus',
  },
  {
    id: 7,
    name: '建议帮助',
    jump: 'advicehelp',
  },
])
const list = reactive([
  {
    title: '产品概况',
    contentList: [
      {
        name: '产品背景',
        jump: 'beingDeveloped',
      },
      {
        name: 'SPD供应链运营服务',
        jump: 'beingDeveloped',
      },
      {
        name: '智能高值耗材柜',
        jump: 'beingDeveloped',
      },
      {
        name: '流程介绍',
        jump: 'beingDeveloped',
      },
    ],
  },
  {
    title: '供应链系列',
    contentList: [
      {
        name: 'OMS管理系统',
        jump: 'OMSManagement',
      },
      {
        name: 'WMS管理系统',
        jump: 'WMSManagement',
      },
      {
        name: '智能账单管理系统',
        jump: 'smartBill',
      },
      {
        name: '智能仓储管理系统',
        jump: 'warehouse',
      },
      {
        name: '智能采购管理系统',
        jump: 'supplyManagement',
      },
      {
        name: '耗材销售及统计系统',
        jump: 'consumables',
      },
    ],
  },
  {
    title: '',
    contentList: [
      {
        name: '骨科智能物流管理系统',
        jump: 'orthopaedic',
      },
      {
        name: '移动在线商城系统',
        jump: 'mobileMall',
      },
      {
        name: '特种设备监管平台',
        jump: 'beingDeveloped',
      },
      {
        name: '病例管理系统',
        jump: 'cases',
      },
      {
        name: '医患交流平台',
        jump: 'beingDeveloped',
      },
      {
        name: '在线学习平台',
        jump: 'beingDeveloped',
      },
    ],
  },
  {
    title: '',
    contentList: [
      {
        name: '医用器械智能柜管理系统',
        jump: 'beingDeveloped',
      },
      {
        name: '医用器械物联网平台',
        jump: 'beingDeveloped',
      },
      {
        name: '智慧商城app',
        jump: 'beingDeveloped',
      },
      {
        name: '跟台管家app',
        jump: 'beingDeveloped',
      },
      {
        name: '骨科材料供应链大数据智能分析平台',
        jump: 'beingDeveloped',
      },
    ],
  },
  {
    title: '智能柜系列',
    contentList: [
      {
        name: '高值耗材智能柜',
        jump: 'beingDeveloped',
      },
      {
        name: '低值耗材智能柜',
        jump: 'beingDeveloped',
      },
      {
        name: '高值耗材智能柜pro',
        jump: 'beingDeveloped',
      },
      {
        name: '低值耗材智能柜pro',
        jump: 'beingDeveloped',
      },
    ],
  },
])
const change = (id: number, jump: string) => {
  console.log('被选中的ID', id)
  selectedTab.value = id
  emit('switchNavigation', jump)
  window.sessionStorage.setItem('tabs', String(id)) //存储
}
const enter = (id: number) => {
  if (id == 2) {
    contentShow.value = true
  } else {
    contentShow.value = false
  }
  productList.value = id
}
const leave = (id: number) => {
  if (id != 2) {
    contentShow.value = false
  }

  productList.value = id
}
const routingHop = (jump: string) => {
  router.push('/' + jump)
  selectedTab.value = 2
}
onMounted(() => {
  setTimeout(() => {
    let num = window.sessionStorage.getItem('tabs')
    if (num != '') {
      selectedTab.value = Number(num)
      console.log(selectedTab)
    }
  }, 300)
})
</script>
<style lang="scss" scoped>
.top {
  width: 100%;
  height: 85px;
  background-color: #3d4653;
  display: flex;
  align-items: center;
  justify-content: space-around;

  // position: fixed;
  .active {
    border-bottom: 5px solid #0087ff;
    // margin-top: 22px;
  }

  img {
    width: 191px;
    height: 52px;
  }

  ul {
    display: flex;
    font-size: 20px;
    font-family: FZLanTingHei-DB-GBK;
    font-weight: 400;
    color: #ffffff;
  }

  .sub-content {
    // width: 100%;
    // height: 100px;
    // background-color: #000;
    display: flex;
    justify-content: center;
    box-sizing: border-box;
    padding-top: 82px;
    height: 500px;
    background: #262b39;
    position: absolute;
    z-index: 99;
    top: 85px;
    left: 0;
    right: 0;
    line-height: 32px;
    overflow: hidden;
  }

  .passDD {
    font-size: 18px;
    color: #999999;
    margin: auto;

    &:hover {
      cursor: pointer;
      color: #0087ff;
    }
  }
}
</style>
