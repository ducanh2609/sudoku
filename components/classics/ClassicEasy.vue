<template>
  <div class="sudoku-play-content">
    <div v-for="(item, index) in quareList" :key="index">
      <SudokuItem :data="item"></SudokuItem>
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
  },
  mounted() {
    this.createArr()
  },
  methods: {
    createArr() {
      const arr = []
      for (let j = 0; j < 9; j++) {
        arr[j] = []
        for (let i = 0; i < 9; i++) {
          let number = Math.ceil(Math.random() * 9)
          while (arr[j].includes(number)) {
            number = Math.ceil(Math.random() * 9)
          }
          arr[j].push(number)
        }
      }
      this.quareList = arr
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
