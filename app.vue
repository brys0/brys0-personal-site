<script setup lang="ts">
</script>

<template>
  <div id="my-site-not-yours">
    <Header />
    <Transition name="page">
      <NuxtPage style="min-height: 100vh; overflow-y: auto;" />
    </Transition>
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