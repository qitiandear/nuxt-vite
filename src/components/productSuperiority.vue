<template>
  <div class="OMS-three">
    <div
      style="font-size: 26px; text-align: center; margin: 70px 0"
      v-show="list[0].titleHidden"
    >
      产品功能
    </div>
    <div class="OMS-three-count" v-for="item in list" :key="item.id">
      <div
        style="
          display: flex;
          justify-content: space-between;
          width: 100%;
          margin-bottom: 52px;
        "
      >
        <div class="OMS-three-png" v-show="item.place == 'left'">
          <img :src="item.pic" alt="" style="width: 100%" />
        </div>
        <div style="width: 610px">
          <div style="font-size: 20px; margin-bottom: 24px; font-weight: 700">
            {{ item.title }}
          </div>
          <div
            style="
              font-size: 16px;
              color: rgba(51, 51, 51, 1);
              margin-bottom: 44px;
            "
            v-html="item.content"
          ></div>
        </div>
        <div class="OMS-three-png" v-show="item.place == 'right'">
          <img :src="item.pic" alt="" style="width: 100%" />
        </div>
      </div>
    </div>
  </div>
</template>
<script setup lang="ts">
interface props {
  list: any[]
}
withDefaults(defineProps<props>(), {
  list: () => [],
})
</script>
<style lang="scss" scoped>
.OMS-three {
  margin: 70px 240px;
  .title {
    height: 172px;
    line-height: 172px;
    font-size: 26px;
    text-align: center;
  }
  .OMS-three-count {
    width: 1440px;
    margin: auto;
    justify-content: space-between;
    .OMS-three-png {
      width: 421px;
    }
  }
}
</style>
