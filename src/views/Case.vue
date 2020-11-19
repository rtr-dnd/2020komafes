<template>
  <div class="wrap" v-bind:class="theme">
    <Header></Header>
    <div class="body">
      <h1>{{caseNameJa}}</h1>
      <section class="one">
        <h2 class="eng">STEP 1</h2>
        <div class="upper-img">
          <p>{{caseNameJa}}での帰り道をカスタマイズしよう</p>
          <div v-if="theme === 'green'" class="sound">
            <img src="../assets/icons/sound-green.svg" alt="">
          </div>
          <div v-if="theme === 'pink'" class="sound">
            <img src="../assets/icons/sound-pink.svg" alt="">
          </div>
          <div v-if="theme === 'purple'" class="sound">
            <img src="../assets/icons/sound-purple.svg" alt="">
          </div>
        </div>
        <div class="img-wrap">
          <div class="img-area" v-bind:class="theme"></div>
        </div>
        <div class="under-img">
          <div class="people">
            <button class="arrow-left">
              <img v-if="theme === 'purple'" src="../assets/icons/purple-left.svg" alt="">
              <img v-if="theme === 'pink'" src="../assets/icons/pink-left.svg" alt="">
              <img v-if="theme === 'green'" src="../assets/icons/green-left.svg" alt="">
            </button>
            <p class="mobile">人数を変える</p>
            <button class="arrow-right">
              <img v-if="theme === 'purple'" src="../assets/icons/purple-right.svg" alt="">
              <img v-if="theme === 'pink'" src="../assets/icons/pink-right.svg" alt="">
              <img v-if="theme === 'green'" src="../assets/icons/green-right.svg" alt="">
            </button>
            <p class="pc">人数を変える</p>
          </div>
          <div class="time">
            <p class="pc">時間帯を変える</p>
            <button class="arrow-left">
              <img v-if="theme === 'purple'" src="../assets/icons/purple-left.svg" alt="">
              <img v-if="theme === 'pink'" src="../assets/icons/pink-left.svg" alt="">
              <img v-if="theme === 'green'" src="../assets/icons/green-left.svg" alt="">
            </button>
            <p class="mobile">時間帯を変える</p>
            <button class="arrow-right">
              <img v-if="theme === 'purple'" src="../assets/icons/purple-right.svg" alt="">
              <img v-if="theme === 'pink'" src="../assets/icons/pink-right.svg" alt="">
              <img v-if="theme === 'green'" src="../assets/icons/green-right.svg" alt="">
            </button>
          </div>
        </div>
      </section>
      <section class="two">
        <h2 class="eng">STEP 2</h2>
        <div class="share-row">
          <div class="twitter">
            <img v-if="theme === 'purple'" src="../assets/icons/twitter-purple.svg" alt="">
            <img v-if="theme === 'pink'" src="../assets/icons/twitter-pink.svg" alt="">
            <img v-if="theme === 'green'" src="../assets/icons/twitter-green.svg" alt="">
          </div>
          <p>あなたの帰り道で生成されたポストカードをシェアしよう</p>
        </div>
      </section>
    </div>
    <Footer v-bind:color="theme"></Footer>
  </div>
</template>

<style lang="scss" scoped>
@import "../assets/variables.scss";

.wrap {
  &.purple {
    background-color: $purple;
    color: $purple-text;
  }
  &.pink {
    background-color: $pink;
    color: $pink-text;
  }
  &.green {
    background-color: $green;
    color: $green-text;
  }
}
.body {
  min-height: 100vh;
  padding: 80px 32px;
  max-width: 800px;
  margin: 0 auto;
}
section {
  padding: 64px 0;
}
h1 {
  text-align: center;
  letter-spacing: 0.2em;
  font-size: 64px;
  @media screen and (max-width: 769px){
    font-size: 48px;
  }
}
h2 {
  font-size: 40px;
  @media screen and (max-width: 769px){
    font-size: 32px;
  }
}
.upper-img {
  width: 80%;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
  p {
    font-size: 14px;
    padding-right: 12px;
  }
  .sound {
    width: 32px;
  }
  @media screen and (max-width: 769px){
    width: 100%;
  }
}
.under-img {
  width: 80%;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  padding-top: 12px;
  @media screen and (max-width: 769px){
    width: 100%;
    flex-direction: column;
    align-items: center;
  }
  button {
    background-color: transparent;
    border: none;
    margin: 0 8px;
    display: flex;
    align-items: center;
    img {
      width: 16px;
    }
  }
  p {
    margin: 0;
    &.pc {
      display: block;
      @media screen and (max-width: 769px){
        display: none;
      }
    }
    &.mobile {
      display: none;
      padding: 24px 12px;
      @media screen and (max-width: 769px){
        display: block;
      }
    }
  }
  .people {
    display: flex;
    align-items: center;
  }
  .time {
    display: flex;
    align-items: center;
  }
}
.share-row {
  width: 80%;
  margin: 0 auto;
  display: flex;
  align-items: center;
  .twitter {
    display: flex;
    align-items: center;
    img {
      width: 48px;
    }
  }
  p {
    margin-left: 16px;
  }
  @media screen and (max-width: 769px){
    width: 100%;
  }
}
.img-wrap {
  position: relative;
  width: 80%;
  padding-top: 46%;
  margin: 8px auto;
  @media screen and (max-width: 769px){
    width: 100%;
    padding-top: 57%;
  }
}
.img-area {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  margin: 0 auto;
  // height: 640px;
  background-image: url(../assets/images/back_city_afternoon.png);
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  border-radius: 12px;
  &.purple {
    border: 2px solid $purple-text;
  }
  &.pink {
    border: 2px solid $pink-text;
  }
  &.green {
    border: 2px solid $green-text;
  }
}
.share-row {
  display: flex;
  align-items: center;
}

</style>

<script>
import Header from '../components/Header'
import Footer from '../components/Footer'

import { imageUrls } from '../image-urls'

export default {
  name: 'Case',
  components: {
    Header,
    Footer
  },
  props: {
    caseName: {
      type: String
    }
  },
  mounted: function () {
    console.log(imageUrls.urban.noon[0])
  },
  computed: {
    caseNameJa: function () {
      switch (this.caseName) {
        case 'urban':
          return '都会'
        case 'resid':
          return '住宅街'
        case 'country':
          return '田舎'
        default:
          return 'このページは存在しません'
      }
    },
    theme: function () {
      switch (this.caseName) {
        case 'urban':
          return 'purple'
        case 'resid':
          return 'pink'
        case 'country':
          return 'green'
        default:
          return ''
      }
    }
  }
}
</script>
