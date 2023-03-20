<template>
  <div class="sudoku-play-content">
    <div v-for="(item, index) in arrSquare" :key="index">
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
      arrSquare: [],
      arrRow: []
    }
  },
  created() {
    this.createArr()
  },
  methods: {
    createArr() {
      for (let j = 0; j < 9; j++) {
        this.arrSquare[j] = { id: j, numberList: [] }
        if ([0, 1, 2].includes(j)) this.rowSingle(0, 1, 2, j)
        else if ([3, 4, 5].includes(j)) this.rowSingle(3, 4, 5, j)
        else this.rowSingle(6, 7, 8, j)
      }
    },
    rowSingle(start, middle, end, j) {
      let index;
      for (let i = 0; i < 9; i++) {
        if ([0, 1, 2].includes(j)) index = 0
        if ([3, 4, 5].includes(j)) index = 3
        if ([6, 7, 8].includes(j)) index = 6
        if ([0, 1, 2].includes(i)) {
          if (!this.arrSquare[middle]) this.arrRow[index] = []
          this.randomNumber(start, middle, end, j, index, 0, 3)
        }
        else if ([3, 4, 5].includes(i)) this.randomNumber(start, middle, end, j, index + 1, 3, 6)
        else this.randomNumber(start, middle, end, j, index + 2, 6, 9)
      }
    },
    randomNumber(start, middle, end, j, k, numStart, numEnd) {
      const arr = [1, 2, 3, 4, 5, 6, 7, 8, 9]
      if (this.arrSquare[end])
        this.arrRow[k] = [...this.arrSquare[start].numberList.slice(numStart, numEnd), ...this.arrSquare[middle].numberList.slice(numStart, numEnd), ...this.arrSquare[end].numberList.slice(numStart, numEnd)]
      else if (this.arrSquare[middle])
        this.arrRow[k] = [...this.arrSquare[start].numberList.slice(numStart, numEnd), ...this.arrSquare[middle].numberList.slice(numStart, numEnd)]
      else
        this.arrRow[k] = [...this.arrSquare[start].numberList.slice(numStart, numEnd)]
      const numberArr = arr.filter(item => !this.arrSquare[j].numberList.includes(item) && !this.arrRow[k].includes(item));
      const randomIndex = Math.ceil(Math.random() * (numberArr.length - 1))
      this.arrSquare[j].numberList.push(numberArr[randomIndex])
    },
    // shuffleArray(array) {
    //   for (let i = array.length - 1; i > 0; i--) {
    //     const j = Math.floor(Math.random() * (i + 1));
    //     [array[i], array[j]] = [array[j], array[i]];
    //   }
    // }
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

  >div {
    border: 1px solid black;
  }
}
</style>
