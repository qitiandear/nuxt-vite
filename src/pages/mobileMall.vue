<template>
  <div class="home">
    <div class="OMS-top"></div>
    <navigationBar @change="change" />
    <div class="mobileMall-one" id="1">
      <div style="text-align: center" v-for="item in list" :key="item.id">
        <img :src="item.pic" alt="" style="width: 208px" />
        <div style="font-size: 28px">
          <i style="font-style: normal">{{ item.title }}</i>
          <i style="font-size: 36px; color: #005bff; font-style: normal">{{
            item.features
          }}</i>
        </div>
      </div>
    </div>
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
    pic: new URL('@/assets/images/mobileMall/pic5.png', import.meta.url).href,
    title: '品类',
    features: '多',
  },
  {
    id: '2',
    pic: new URL('@/assets/images/mobileMall/pic2.png', import.meta.url).href,
    title: '物流',
    features: '快',
  },
  {
    id: '3',
    pic: new URL('@/assets/images/mobileMall/pic3.png', import.meta.url).href,
    title: '货品',
    features: '好',
  },
  {
    id: '4',
    pic: new URL('@/assets/images/mobileMall/pic4.png', import.meta.url).href,
    title: '资金',
    features: '省',
  },
  {
    id: '5',
    pic: new URL('@/assets/images/mobileMall/pic1.png', import.meta.url).href,
    title: '更',
    features: '安全',
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
  background: url('@/assets/images/mobileMall/banner.png');
  background-size: cover;
  color: #ffffff;
  box-sizing: border-box;
  padding-top: 135px;
  padding-left: 291px;
}
.mobileMall-one {
  margin: 83px 277px;
  display: flex;
  justify-content: space-between;
}
</style>
