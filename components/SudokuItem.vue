<template>
  <div class="sudoku-number-box">
    <div v-for="(item, index) in data" :key="index" class="sudoku-number">
      {{ item }}
    </div>
  </div>
</template>
<script>
export default {
  props: {
    data: { type: Array, default: null }
  }
}
</script>
<style lang="scss" scoped>
.sudoku-number-box {
  height: 100%;
  display: grid;
  grid-template-columns: repeat(3, calc(100% / 3));
  grid-template-rows: repeat(3, calc(100% / 3));

  .sudoku-number {
    border: 1px solid rgb(180, 178, 178);
    font-size: 40px;
    text-align: center;

    &:hover {
      cursor: pointer;
      background-color: rgb(228, 228, 228);
    }
  }
}
</style>
