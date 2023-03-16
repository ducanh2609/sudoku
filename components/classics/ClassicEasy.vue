<template>
  <div class="sudoku-play-content">
    <div v-for="(item, index) in quareList" :key="index">
      {{ item }}
      <SudokuItem></SudokuItem>
    </div>
  </div>
</template>
<script>
import SudokuItem from '../SudokuItem.vue'

export default {
  components: {
    SudokuItem
  },
  data() {
    return {
      quareList: new Array(9)
    }
  }
}
</script>
<style lang="scss" scoped>
.sudoku-play-content {
  border: 1px solid rgb(0, 0, 0);
  height: 60vh;
  display: grid;
  grid-template-columns: repeat(3, calc(100% / 3));
  grid-template-rows: repeat(3, calc(100% / 3));
  > div {
    border: 1px solid black;
  }
}
</style>
