<template>
  <div>
    <HeaderDefault />
    <Nuxt />
  </div>
</template>
<script>
import HeaderDefault from '~/components/HeaderDefault.vue'
export default {
  components: {
    HeaderDefault
  }
}
</script>
<style lang="scss">
body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}
</style>
