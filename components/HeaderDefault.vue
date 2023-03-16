<template>
  <div class="header-default">
    <h1>Sudoku.com</h1>
    <nuxt-link to="/classic" tag="p"><span>Cổ điển</span></nuxt-link>
    <nuxt-link to="/killer" tag="p"><span>Killer</span></nuxt-link>
  </div>
</template>
<script>
export default {}
</script>
<style lang="scss" scoped>
.header-default {
  border-bottom: 1px solid rgb(199, 197, 197);
  height: 70px;
  padding: 0 19%;
  display: flex;
  line-height: 70px;
  h1 {
    margin: 0;
  }
  p {
    font-size: 20px;
    margin: 0 0 0 50px;
    &:hover {
      cursor: pointer;
    }
    span {
      padding: 10px;
      border-radius: 3px;
      &:hover {
        cursor: pointer;
        background-color: rgb(199, 197, 197);
      }
    }
  }
  .nuxt-link-active {
    border-bottom: 2px solid blue;
  }
}
</style>
