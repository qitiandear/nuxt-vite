<template>
  <div>
    <div class="shuffling">
      <el-carousel trigger="click" height="700px" autoplay>
        <el-carousel-item v-for="item in bannerList" :key="item.id">
          <el-image
            :src="item.img"
            fit="cover"
            style="height: 100%; width: 100%"
          />
        </el-carousel-item>
      </el-carousel>

      <div
        style="
          position: absolute;
          bottom: -60px;
          z-index: 99;
          display: flex;
          left: 50%;
          transform: translateX(-50%);
        "
      >
        <div
          class="banner-content"
          v-for="(item, index) in shufflingList"
          :key="index"
        >
          <el-image :src="item.photograph" class="productImg" />
          <div style="margin-right: 22px; text-align: left">
            <div>
              {{ item.title }}
            </div>
            <div style="font-size: 14px">
              <span
                style="margin-right: 15px"
                v-for="(temp, index) in item.list"
                :key="index"
                >{{ temp.name }}</span
              >
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="banner02">
      <img src="@/assets/images/banner02.png" alt="" class="banner02Img" />
    </div>
  </div>
</template>
<script setup lang="ts">
const bannerList = reactive([
  {
    img: new URL('@/assets/images/banner01.png', import.meta.url).href,
    id: 1,
  },
  {
    img: new URL('@/assets/images/certificate.jpg', import.meta.url).href,
    id: 2,
  },
])
const shufflingList = reactive([
  {
    photograph: new URL('@/assets/images/ComputerSoftware.png', import.meta.url)
      .href,
    title: 'SPD建设-软件',
    list: [
      {
        id: 1,
        name: '供应商管理',
      },
      {
        id: 2,
        name: '采购管理',
      },
      {
        id: 3,
        name: '库存管理',
      },
      {
        id: 4,
        name: '精准消耗',
      },
      {
        id: 5,
        name: '物资溯源',
      },
    ],
  },
  {
    photograph: new URL(
      '@/assets/images/ComputerSchematic.png',
      import.meta.url
    ).href,
    title: 'SPD建设-硬件',
    list: [
      {
        id: 1,
        name: '智能高值耗材柜',
      },
      {
        id: 2,
        name: 'RFID技术',
      },
      {
        id: 3,
        name: '超高频PDA',
      },
    ],
  },
  {
    photograph: new URL('@/assets/images/productDesign.png', import.meta.url)
      .href,
    title: 'SPD服务-运营服务',
    list: [
      {
        id: 1,
        name: 'GSP合规质量辅助',
      },
      {
        id: 2,
        name: '量化指标',
      },
      {
        id: 3,
        name: '科学管理流程',
      },
    ],
  },
  {
    photograph: new URL(
      '@/assets/images/EngineeringDrawing.png',
      import.meta.url
    ).href,
    title: 'SPD售后-售后支持',
    list: [
      {
        id: 1,
        name: '7*24小时',
      },
      {
        id: 2,
        name: '技术专业',
      },
      {
        id: 3,
        name: '操作规范',
      },
      {
        id: 4,
        name: '操作规范',
      },
    ],
  },
])
</script>
<style lang="scss" scoped>
.shuffling {
  position: relative;

  ::v-deep(.el-carousel__indicators--horizontal) {
    bottom: 60px;
  }

  .the-text {
    // width: 700px;
    // font-size: 90px;
    position: absolute;
    top: 18%;
    left: 17%;
    z-index: 99;
    color: #fff;

    .the-text-content {
      width: 632px;
      height: 43px;
      line-height: 43px;
      // text-align: center;
      background: #ffffff;
      border-radius: 10px;
      font-size: 16px;
      color: #3d4653;
      margin-bottom: 10px;
      padding-left: 16px;
      padding-right: 16px;
    }
  }

  .banner-content {
    // position: absolute;
    // bottom: -60px;
    // z-index: 99;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 330px;
    height: 120px;
    background: #ffffff;
    box-shadow: 0px 16px 35px 0px rgba(0, 0, 0, 0.08);
    border-radius: 5px;
    margin-right: 45px;
  }

  .productImg {
    width: 57px;
    flex-shrink: 0;
    height: 47px;
    margin: 0 17px 0 13px;
  }
}

.banner02 {
  height: 160px;
  margin-top: 108px;
  text-align: center;

  .banner02Img {
    height: 100%;
  }
}
</style>
