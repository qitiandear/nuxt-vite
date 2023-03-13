<template>
  <div class="mangement">
    <div style="padding-left: 250px; padding-top: 489px">
      <div style="font-size: 24px">请选择您要登录的管理平台</div>
      <div class="mangent-conteng">
        <el-link
          href="http://182.92.98.230:81/index"
          target="_blank"
          class="mangent-top"
        >
          <img
            src="@/assets/images/Management/supplier.png"
            alt=""
            class="mangent-png"
          />
          <div style="text-align: center">供应商平台</div>
        </el-link>
        <el-link href="/beingDeveloped" target="_blank" class="mangent-top">
          <img
            src="@/assets/images/Management/hospital.png"
            alt=""
            class="mangent-png"
          />
          <div style="text-align: center">医院平台</div>
        </el-link>
        <el-link href="/beingDeveloped" target="_blank" class="mangent-top">
          <img
            src="@/assets/images/Management/operating.png"
            alt=""
            class="mangent-png"
          />
          <div style="text-align: center">运营平台</div>
        </el-link>
      </div>
    </div>
  </div>
</template>
<script setup lang="ts">
import supplier from '@/assets/images/Management/supplier.png'
import hospital from '@/assets/images/Management/hospital.png'
import operating from '@/assets/images/Management/operating.png'
const list = reactive([
  {
    img: supplier,
    text: '供应商平台',
  },
  {
    img: hospital,
    text: '医院平台',
  },
  {
    img: operating,
    text: '运营平台',
  },
])
</script>

<style lang="scss" scoped>
::v-deep(.el-link__inner) {
  display: block;
}
.mangement {
  color: #ffffff;
  font-size: 26px;
  background: url('@/assets/images/Management/top.png');
  background-size: cover;
  height: 995px;
  .mangent-conteng {
    display: flex;
    margin-top: 43px;
    font-size: 23px;
    .mangent-top {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      font-size: 23px;
      color: #ffffff;
      width: 210px;
      height: 280px;
      background: rgba(0, 91, 255, 0.5);
      margin-right: 70px;
      .mangent-png {
        width: 125px;
        margin-bottom: 27px;
      }
      &:hover {
        background: rgba(0, 91, 255, 1);
      }
    }
  }
}
</style>
