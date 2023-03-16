<template>
  <div class="sudoku-number-box">
    <div v-for="(item, index) in quareList" :key="index" class="sudoku-number">
      {{ item }}
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      quareList: new Array(9)
    }
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

    &:hover {
      cursor: pointer;
      background-color: rgb(228, 228, 228);
    }
  }
}
</style>
