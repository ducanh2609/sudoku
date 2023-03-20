<template>
  <div v-if="data" class="sudoku-number-box">
    <div v-for="(item, index) in data.numberList" :key="index" class="sudoku-number">
      {{ item }}
    </div>
  </div>
</template>
<script>
export default {
  props: {
    data: { type: Object, default: null }
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
    font-size: 35px;
    text-align: center;

    &:hover {
      cursor: pointer;
      background-color: rgb(228, 228, 228);
    }
  }
}
</style>
