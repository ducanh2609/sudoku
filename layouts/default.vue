<template>
  <div>
    <HeaderDefault />
    <div class="sudoku-page">
      <div class="sudoku-box">
        <div class="sudoku-play">
          <div class="sudoku-play-box">
            <div class="sudoku-play-sidebar">
              <i>Độ khó:</i>
              <nuxt-link to="/classic/de" tag="span">Dễ</nuxt-link>
              <nuxt-link to="/classic/tb" tag="span">Trung Bình</nuxt-link>
              <nuxt-link to="/classic/kho" tag="span">Khó</nuxt-link>
              <nuxt-link to="/classic/cgia" tag="span">Chuyên gia</nuxt-link>
              <nuxt-link to="/classic/acquy" tag="span">Ác quỷ</nuxt-link>
            </div>
            <Nuxt />
          </div>
          <div class="sudoku-play-number">
            <div class="sudoku-number-notify">
              <div>Lỗi: <span class="sudoku-error-limit">0</span>/3</div>
              <span class="sudoku-time">0:00</span>
            </div>
            <div class="sudoku-number-sidebar">
              <div><i class="fa-solid fa-rotate-left"></i></div>
              <div><i class="fa-solid fa-eraser"></i></div>
              <div><i class="fa-solid fa-pencil"></i></div>
              <div><i class="fa-solid fa-puzzle-piece"></i></div>
            </div>
            <div class="sudoku-number-content">
              <div v-for="(number, index) in numberList" :key="index">
                {{ number }}
              </div>
            </div>
            <div class="new-game">Trò chơi mới</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import HeaderDefault from '~/components/HeaderDefault.vue'
export default {
  components: {
    HeaderDefault
  },
  data() {
    return {
      numberList: [1, 2, 3, 4, 5, 6, 7, 8, 9]
    }
  }
}
</script>
<style lang="scss">
body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  .sudoku-page {
    min-height: calc(100vh - 73px);
    box-sizing: border-box;

    .sudoku-box {
      width: 70%;
      margin: 0 auto;

      .sudoku-play {
        height: 65vh;
        margin: 30px 0;
        display: flex;
        justify-content: space-between;

        .sudoku-play-box {
          width: 60vh;

          .sudoku-play-sidebar {
            height: 5vh;
            font-size: 16px;

            i {
              font-weight: 600;
              margin-right: 20px;
            }

            span {
              margin-right: 15px;

              &:hover {
                cursor: pointer;
                color: blue;
              }
            }

            .nuxt-link-exact-active {
              color: blue;
            }
          }
        }

        .sudoku-play-number {
          width: 40vh;

          .sudoku-number-notify {
            display: flex;
            justify-content: space-around;
            height: 5vh;
          }

          .sudoku-number-sidebar {
            height: 10vh;
            display: grid;
            grid-template-columns: repeat(4, 25%);
            box-sizing: border-box;

            > div {
              margin: 1vh;
              border-radius: 50%;
              display: flex;
              flex-direction: column;
              justify-content: center;
              text-align: center;
              background-color: rgb(137, 201, 230);

              &:hover {
                cursor: pointer;
                background-color: rgba(137, 201, 230, 0.705);
              }

              i {
                font-size: 30px;
                color: blue;
              }
            }
          }

          .sudoku-number-content {
            margin-top: 1vh;
            height: 40vh;
            display: grid;
            grid-template-columns: repeat(3, calc(100% / 3));
            grid-template-rows: repeat(3, calc(100% / 3));

            > div {
              background-color: rgb(137, 201, 230);
              margin: 0.5vh;
              border-radius: 3px;
              font-size: 50px;
              text-align: center;
              line-height: 12vh;
              color: blue;

              &:hover {
                cursor: pointer;
                background-color: rgba(0, 0, 255, 0.44);
              }
            }
          }

          .new-game {
            margin-top: 1vh;
            height: 8vh;
            border-radius: 5px;
            font-size: 20px;
            text-align: center;
            line-height: 8vh;
            background-color: rgb(25, 133, 210);
            color: white;
            font-weight: 600;

            &:hover {
              cursor: pointer;
              background-color: rgba(25, 133, 210, 0.807);
            }
          }
        }
      }
    }
  }
}
</style>
