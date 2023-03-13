<template>
  <div>
    <NuxtLayout name="header" @switchNavigation="switchNavigation" />
    <slot />
    <NuxtLayout name="footer" />
  </div>
</template>

<script setup lang="ts">
const router = useRouter()
const navigationID = ref(1)
const switchNavigation = (jump: string) => {
  navigationID.value = Number(jump)
  router.push('/' + jump)
}

onMounted(() => {
  window.sessionStorage.setItem('tabs', '1') //存储
})
</script>
