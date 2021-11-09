<template>
  <div>
    <v-container fluid class="mainBlock">
      <v-container>
        <div class="block-title mb-12 mt-16">Робота з нами</div>
        <div class="d-flex justify-center">
          <table style="border-collapse: collapse">
            <tr>
              <td
                v-for="(item, index) in items"
                :key="index"
                style="vertical-align: top"
              >
                <div class="item-text" v-if="item.top">
                  {{ item.text }}
                </div>
              </td>
            </tr>
            <tr>
              <td
                v-for="(item, index) in items"
                :key="index"
                style="vertical-align: top"
              >
                <div class="item-figure item-figure-top" v-if="item.top">
                  {{ item.number | twoDigits }}
                </div>
              </td>
            </tr>

            <tr>
              <td
                v-for="(item, index) in items"
                :key="index"
                style="vertical-align: top"
              >
                <div class="item-figure item-figure-bottom" v-if="!item.top">
                  {{ item.number | twoDigits }}
                </div>
              </td>
            </tr>

            <tr>
              <td
                v-for="(item, index) in items"
                :key="index"
                style="vertical-align: top"
              >
                <div class="item-text" v-if="!item.top">
                  {{ item.text }}
                </div>
              </td>
            </tr>
          </table>
        </div>
      </v-container>
    </v-container>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data () {
    return {
      items: [
        {
          text: 'Внесення накладних з обладнанням та ліцензіями',
          number: 1,
          top: true
        },
        {
          text: 'Перегляд предметів та приміщення у якому їх встановлено ',
          number: 2,
          top: false
        },
        {
          text: 'Перегляд предметів та їх власників',
          number: 3,
          top: true
        },
        {
          text: 'Перегляд обладнання з індивідуальними QR-кодами',
          number: 4,
          top: false
        },
        {
          text: 'Передача обладнання між власникам',
          number: 5,
          top: true
        },
        {
          text: 'Відправлення обладнання у ремонт',
          number: 6,
          top: false
        },
        {
          text: 'Списання обладнання',
          number: 7,
          top: true
        },
        {
          text: 'Утилізація обладнання',
          number: 8,
          top: false
        }
      ]
    }
  },
  filters: {
    twoDigits: value => {
      if (value.toString().length === 1) {
        return `0${value}`
      }
      return value
    }
  }
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css?family=Nunito');
@import url('https://fonts.googleapis.com/css?family=Roboto');

.block-title {
  text-align: center;
  font-family: Roboto,serif;
  font-style: normal;
  font-weight: normal;
  font-size: 48px;
  line-height: 56px;
}

.mainBlock {
  background: url("../components/img.svg") no-repeat center;
  min-height: 645px;
}

.item-figure-top {
  position: relative;
  bottom: -1px;
  background: url("../components/figureTop.svg") no-repeat center;
}

.item-figure-bottom {
  position: relative;
  top: -1px;
  background: url("../components/figureDown.svg") no-repeat center;
}

.item-figure {
  width: 180px;

  text-align: center;

  font-family: Nunito,serif;
  font-style: normal;
  font-weight: bold;
  color: #FFFFFF;
  line-height: 1.25;

  font-size: 68px;
  min-height: 89px;
}

.item-text {
  width: 180px;

  font-family: Nunito,serif;
  font-style: normal;
  font-weight: normal;
  font-size: 18px;
  line-height: 25px;

  color: #000000;
}
</style>
