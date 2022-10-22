<script setup lang="ts">
useHead({
  meta: [
    {
      property: 'og:type',
      content: 'website'
    },
    {
      property: 'og:site_name',
      content: 'Brys\' Personal Site'
    },
    {
      property: 'theme-color',
      content: '#ff9142'
    }
  ]
})
</script>

<template>
  <div id="my-site-not-yours">
    <Header />
    <NuxtPage style="min-height: 100vh; overflow-y: auto;" v-slot="{ Component }">
      <Transition name="page">
        <component :is="Component" />
      </Transition>
    </NuxtPage>

    <Footer />
  </div>

</template>


<style lang="scss" scoped>
#__nuxt {
  min-height: 100vh;
}

#my-site-not-yours {
  min-height: 100vh;

}
</style>