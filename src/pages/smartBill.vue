<template>
  <div class="home">
    <div class="OMS-top">
      <div style="font-size: 60px; margin-bottom: 10px">智能账单管理系统</div>
      <div style="font-size: 26px">
        账单管理软件可以减轻管理者的工作任务，提高工作效率
      </div>
      <div style="font-size: 26px">
        减少失误风险，是经营管理不可或缺的一个好帮手
      </div>
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
    <div class="OMS-one" id="1">
      <div
        class="OMS-one-content"
        v-for="(item, index) in topList"
        :key="index"
      >
        <div class="OMS-content-png">
          <img :src="item.img" alt="" style="width: 100%" />
        </div>
        <div class="title">{{ item.title }}</div>
        <div class="content">{{ item.content }}</div>
      </div>
    </div>
    <div class="OMS-two" id="2">
      <div class="title">产品应用价值</div>
      <div class="OMS-two-content">
        <div
          class="OMS-two-top"
          v-for="(item, index) in worthList"
          :key="index"
        >
          <div class="OMS-two-png">
            <img :src="item.img" alt="" style="width: 100%" />
          </div>
          <div class="OMS-two-title">
            <div
              style="
                width: 7px;
                height: 19px;
                background: #0087ff;
                margin-right: 9px;
              "
            ></div>
            {{ item.title }}
          </div>
          <div class="OMS-two-bottom">
            <div
              style="display: flex; align-items: center"
              v-for="(temp, index) in item.list"
              :key="index"
            >
              <div
                style="
                  width: 10px;
                  height: 2px;
                  background: #333333;
                  margin-right: 8px;
                "
              ></div>
              {{ temp.name }}
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="OMS-three" id="3">
      <div class="title">产品功能</div>
      <div
        class="OMS-three-count"
        v-for="(item, index) in functionList"
        :key="index"
      >
        <div style="margin-right: 52px; width: 106px">
          <img :src="item.img" alt="" style="width: 106px" />
        </div>
        <div>
          <div class="OMS-three-top">{{ item.title }}</div>
          <div class="OMS-three-bottom">{{ item.content }}</div>
        </div>
      </div>
    </div>
    <div style="width: 1440px; margin: auto; margin-bottom: 188px" id="4">
      <img
        src="@/assets/images/OMS01/bottompng.png"
        alt=""
        style="width: 100%"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
import { HomeFilled, ArrowRight } from '@element-plus/icons-vue'
const index = ref(1)
const newList = reactive([
  {
    title: '产品优势',
    id: 1,
  },
  {
    title: '产品应用价值',
    id: 2,
  },
  {
    title: '产品功能',
    id: 3,
  },
  {
    title: '免费试用',
    id: 4,
  },
])
const topList = reactive([
  {
    img: new URL('@/assets/images/billManagement/data.png', import.meta.url)
      .href,
    title: '支持多数据源、多数据格式',
    content:
      '系统支持数据库访问、文本文件、XML文件等多种数据来源，并可参数定制数据来源文件的数据格式。',
  },
  {
    img: new URL(
      '@/assets/images/billManagement/screening.png',
      import.meta.url
    ).href,
    title: '个性化纬度筛选及各类数据',
    content:
      '可根据客户类型、账户种类、客户群体、消费习惯等多维度个性化定制账单格式。',
  },
  {
    img: new URL('@/assets/images/billManagement/send.png', import.meta.url)
      .href,
    title: '多渠道统一发送与管理',
    content:
      '支持纸质、电子、短信等多渠道发送账单，并可参数化定制客户的账单发送渠道。',
  },
  {
    img: new URL('@/assets/images/billManagement/online.png', import.meta.url)
      .href,
    title: '账单联机',
    content: '历史账单查询；冻结/解冻账单；查询冻结/解冻明细；查询补打明细。',
  },
])
const worthList = reactive([
  {
    img: new URL('@/assets/images/OMS01/customer.png', import.meta.url).href,
    title: '解决客户管理难题',
    list: [
      { name: '客户管理集成化' },
      { name: '合同执行流程化' },
      { name: '售后服务自动化' },
      { name: '客户统计智能化' },
    ],
  },
  {
    img: new URL('@/assets/images/OMS01/product.png', import.meta.url).href,
    title: '解决产品管理难题',
    list: [
      { name: '产品管理统一化' },
      { name: '数据更新实时化' },
      { name: '品类层次多样化' },
      { name: '产品数据共享化' },
    ],
  },
  {
    img: new URL('@/assets/images/OMS01/bill.png', import.meta.url).href,
    title: '解决账单管理难题',
    list: [
      { name: '账单分类标准化' },
      { name: '变更管理一体化' },
      { name: '执行过程可视化' },
      { name: '账单结算多样化' },
    ],
  },
  {
    img: new URL('@/assets/images/OMS01/after-sales.png', import.meta.url).href,
    title: '解决售后管理难题',
    list: [
      { name: '售后响应实时化' },
      { name: '任务分配自动化' },
      { name: '售后管控科学化' },
      { name: '售后统计精准化' },
    ],
  },
  {
    img: new URL('@/assets/images/OMS01/warehouse.png', import.meta.url).href,
    title: '解决库房管理难题',
    list: [
      { name: '库房管理集成化' },
      { name: '出入库执行流程化' },
      { name: '库房统计精准化' },
      { name: '货品溯源智能化' },
    ],
  },
  {
    img: new URL('@/assets/images/OMS01/procurement.png', import.meta.url).href,
    title: '解决采购管理难题',
    list: [
      { name: '采购执行流程化' },
      { name: '合同执行流程化' },
      { name: '采购更新实时化' },
      { name: '采购数据共享化' },
    ],
  },
])
const functionList = reactive([
  {
    img: new URL('@/assets/images/billManagement/toLead.png', import.meta.url)
      .href,
    title: '数据导入',
    content:
      '账单数据完整性、合法性、正确性校验；业务逻辑异常后的业务级回滚（如积分异常），账单拦截；综合账单的账户合并。',
  },
  {
    img: new URL('@/assets/images/billManagement/bill.png', import.meta.url)
      .href,
    title: '账单生成',
    content:
      '海量作业动态调度；HTML格式账单文件生成；账单生成短信提醒；积分到期短信提醒；账单打印作业抽样；高端用户年度账单生成。',
  },
  {
    img: new URL(
      '@/assets/images/billManagement/personalized.png',
      import.meta.url
    ).href,
    title: '个性化规则管理',
    content:
      '个性化优先级设定、个性化规则复核、个性化规则设定、修改、指定选用模板；账单模板启用时效设置；模板可变图片区的广告管理；模板空白区域管理；客户消费行为数据分析。',
  },
])
const change = (id: number) => {
  index.value = id
}
</script>
<style lang="scss" scoped>
.OMS-top {
  height: 500px;
  background: url('@/assets/images/billManagement/banner.png');
  background-size: cover;
  color: #ffffff;
  box-sizing: border-box;
  padding-top: 135px;
  padding-left: 291px;
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
.OMS-one {
  height: 492px;
  width: 1440px;
  display: flex;
  align-items: center;
  margin: auto;
  > :last-child {
    margin-right: 0;
  }
  .OMS-one-content {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 320px;
    height: 340px;
    background: #ffffff;
    padding: 0 30px;
    box-sizing: border-box;
    margin-right: 53px;
    border: 1px solid #e5e5e5;
    .OMS-content-png {
      width: 119px;
      margin-bottom: 36px;
    }
    .title {
      font-size: 20px;
      margin-bottom: 24px;
    }
    .content {
      font-size: 16px;
    }
  }
}
.OMS-two {
  // width: 1920px;
  height: 410px;
  background: #f0f0f0;
  text-align: center;
  .title {
    font-size: 26px;
    color: #333333;
    padding: 40px 0;
  }
  .OMS-two-content {
    width: 1470px;
    margin: auto;
    display: flex;
    > :last-child {
      margin-right: 0;
    }
    .OMS-two-top {
      width: 160px;
      display: flex;
      flex-direction: column;
      align-items: center;
      margin-right: 84px;
      .OMS-two-png {
        width: 49px;
      }
      .OMS-two-title {
        display: flex;
        align-items: center;
        font-size: 18px;
        margin-top: 37px;
        margin-bottom: 25px;
      }
      .OMS-two-bottom {
        font-size: 14px;
        color: #333333;
      }
    }
  }
}
.OMS-three {
  .title {
    height: 172px;
    line-height: 172px;
    font-size: 26px;
    text-align: center;
  }
  .OMS-three-count {
    display: flex;
    width: 1000px;
    height: 245px;
    align-items: center;
    margin: auto;
    .OMS-three-top {
      font-size: 20px;
      margin-bottom: 26px;
      color: rgba(51, 51, 51, 1);
    }
    .OMS-three-bottom {
      font-size: 18px;
      color: #333333;
    }
  }
}
</style>
