<template>
  <div>
    <nuxt-child />
  </div>
</template>
<script>
export default {
  mounted() {
    this.$router.push('/classic/de')
  }
}
</script>
<style lang="scss" scoped></style>
