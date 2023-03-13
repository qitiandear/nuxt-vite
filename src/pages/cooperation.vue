<template>
  <div class="mangement">
    <div class="top">
      <el-image
        :src="topImg"
        style="width: 100%"
        fit="cover"
        class="top-content"
      />
    </div>
    <img src="@/assets/images/partners/top1.png" alt="" style="width: 100%" />
    <div style="margin: 60px 240px">
      <div
        style="
          font-size: 34px;
          color: #333333;
          font-family: FZLanTingHei-DB-GBK;
          margin-bottom: 14px;
        "
      >
        合作医院
      </div>
      <div
        style="
          font-size: 18px;
          color: #333333;
          font-family: FZLanTingHeiS-EL-GB;
          margin-bottom: 60px;
        "
      >
        无缝对接医院HIS系统，帮助医院更好更快的完成手术
      </div>
      <div class="partner-content">
        <div class="partner-content-big" v-for="item in list" :key="item.id">
          <img :src="item.pic" alt="" class="top-content" />
          <div class="partner-content-info">
            {{ item.content }}
          </div>
        </div>
      </div>
    </div>

    <img src="@/assets/images/partners/bottom.png" alt="" style="width: 100%" />
  </div>
</template>
<script setup lang="ts">
import topImg from '@/assets/images/partners/top.png'
import pic1 from '@/assets/images/partners/pic1.png'
import pic2 from '@/assets/images/partners/pic2.png'
import pic3 from '@/assets/images/partners/pic3.png'
import pic4 from '@/assets/images/partners/pic4.png'
import pic5 from '@/assets/images/partners/pic5.png'
import pic6 from '@/assets/images/partners/pic6.png'
const list = reactive([
  {
    id: 1,
    pic: pic1,
    content: '太原市中心医院- 汾东院区',
  },
  {
    id: 2,
    pic: pic2,
    content: '长治市第二人民医院',
  },
  {
    id: 3,
    pic: pic3,
    content: '汾西矿务局总医院',
  },
  {
    id: 4,
    pic: pic4,
    content: '长治市人民医院',
  },
  {
    id: 5,
    pic: pic5,
    content: '大同市第二人民医院',
  },
  {
    id: 6,
    pic: pic6,
    content: '娄烦县人民医院',
  },
])
</script>
<style lang="scss" scoped>
* {
  margin: 0;
  padding: 0;
}
.top {
  height: 500px;
  // width: 1889px;
  .top-content {
    // width: 100%;
    display: block;
    height: 100%;
  }
}
// .mangement {
//   background-color: #fff;
// //   text-align: center;
//   font-size: 26px;
// }
.partner-content {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;

  .partner-content-big {
    // height: 270px;
    width: 450px;
    margin-bottom: 60px;
    .top-content {
      width: 100%;
      display: block;
    }
    .partner-content-info {
      color: #fff;
      height: 75px;
      // width: 450px;
      background: #3d4653;
      padding-left: 20px;
      line-height: 75px;
    }
  }
}
</style>
