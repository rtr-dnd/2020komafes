<template>
  <div class="wrap" v-bind:class="theme">
    <div class="body">
      <h1>{{caseNameJa}}</h1>
      <section class="one">
        <h2 class="eng">STEP 1</h2>
        <div class="upper-img">
          <p>{{caseNameJa}}での帰り道をカスタマイズしよう</p>
          <div v-on:click="play" v-bind:class="[isPlayingAudio ? 'playing' : '']" v-if="theme === 'green'" class="sound">
            <img src="../assets/icons/sound-green.svg" alt="">
          </div>
          <div v-on:click="play" v-bind:class="[isPlayingAudio ? 'playing' : '']" v-if="theme === 'pink'" class="sound">
            <img src="../assets/icons/sound-pink.svg" alt="">
          </div>
          <div v-on:click="play" v-bind:class="[isPlayingAudio ? 'playing' : '']" v-if="theme === 'purple'" class="sound">
            <img src="../assets/icons/sound-purple.svg" alt="">
          </div>
          <audio id="audio">
            <source :src="require('../assets/audio/' + audioName + '.mp3')">
          </audio>
        </div>
        <div class="img-wrap">
          <div class="img-area" v-bind:class="[theme, isNight ? 'night' : '']"></div>
          <img v-if="peopleNum !== -1" :src="require('../assets/people/' + imgName + '.png')" class="img-overlay" v-bind:class="[theme]">
        </div>
        <div class="under-img">
          <div class="people">
            <button class="arrow-left" v-on:click="decreasePeople">
              <img v-if="theme === 'purple'" src="../assets/icons/purple-left.svg" alt="">
              <img v-if="theme === 'pink'" src="../assets/icons/pink-left.svg" alt="">
              <img v-if="theme === 'green'" src="../assets/icons/green-left.svg" alt="">
            </button>
            <p class="mobile">人数を変える</p>
            <button class="arrow-right" v-on:click="increasePeople">
              <img v-if="theme === 'purple'" src="../assets/icons/purple-right.svg" alt="">
              <img v-if="theme === 'pink'" src="../assets/icons/pink-right.svg" alt="">
              <img v-if="theme === 'green'" src="../assets/icons/green-right.svg" alt="">
            </button>
            <p class="pc">人数を変える</p>
          </div>
          <div class="time">
            <p class="pc">時間帯を変える</p>
            <button class="arrow-left" v-on:click="changeTime">
              <img v-if="theme === 'purple'" src="../assets/icons/purple-left.svg" alt="">
              <img v-if="theme === 'pink'" src="../assets/icons/pink-left.svg" alt="">
              <img v-if="theme === 'green'" src="../assets/icons/green-left.svg" alt="">
            </button>
            <p class="mobile">時間帯を変える</p>
            <button class="arrow-right" v-on:click="changeTime">
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
          <a class="twitter"
            :href="tweetHref" rel="nofollow" target="_blank" title="Twitterで共有">
            <div class="twitter">
              <img v-if="theme === 'purple'" src="../assets/icons/twitter-purple.svg" alt="">
              <img v-if="theme === 'pink'" src="../assets/icons/twitter-pink.svg" alt="">
              <img v-if="theme === 'green'" src="../assets/icons/twitter-green.svg" alt="">
            </div>
            <p>あなたの帰り道で生成されたポストカードをシェアしよう</p>
          </a>
        </div>
      </section>
      <a class="back-wrap" href="/">
        <button v-bind:class="theme" class="back">
          トップに戻る
        </button>
      </a>
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
    opacity: 0.4;
    &.playing {
      opacity: 1.0;
    }
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
  a {
    color: inherit;
    text-decoration: none;
  }
  p {
    margin-left: 16px;
    color: inherit;
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
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
  border-radius: 12px;
  &.purple {
    border: 2px solid $purple-text;
    background-image: url(../assets/images/back_city_afternoon.png);
    &.night {
      background-image: url(../assets/images/back_city_night.png);
    }
  }
  &.pink {
    border: 2px solid $pink-text;
    background-image: url(../assets/images/back_residental_afternoon.png);
    &.night {
      background-image: url(../assets/images/back_residental_night.png);
    }
  }
  &.green {
    border: 2px solid $green-text;
    background-image: url(../assets/images/back_inaka_afternoon.png);
    &.night {
      background-image: url(../assets/images/back_inaka_night.png);
    }
  }
}
.img-overlay {
  display: block;
  width: calc(100% - 4px);
  height: calc(100% - 4px);
  position: absolute;
  z-index: 1;
  top: 2px;
  left: 2px;
  right: 2px;
  bottom: 2px;
  margin: 0 auto;
  object-fit: cover;
}
.share-row {
  display: flex;
  align-items: center;
}

.back-wrap {
  display: block;
  margin: 0 auto;
  text-align: center;
}

button.back {
  display: inline-block;
  text-align: center;
  text-decoration: none;
  background-color: transparent;
  cursor: pointer;
  transition: 0.3s;
  font-weight: 500;
  border-radius: 8px;
  border: 2px solid;
  box-shadow: none;
  padding: 16px 40px;
  &.purple {
    background-color: transparent;
    color: $purple-text;
    border-color: $purple-text;
    &:hover {
      background-color: $purple-text;
      color: $purple;
    }
  }
  &.pink {
    background-color: transparent;
    color: $pink-text;
    border-color: $pink-text;
    &:hover {
      background-color: $pink-text;
      color: $pink;
    }
  }
  &.green {
    background-color: transparent;
    color: $green-text;
    border-color: $green-text;
    &:hover {
      background-color: $green-text;
      color: $green;
    }
  }
}

</style>

<script>
import Footer from '../components/Footer'

import { imageUrls } from '../image-urls'

export default {
  name: 'Case',
  components: {
    Footer
  },
  props: {
    caseName: {
      type: String
    }
  },
  mounted: function () {
    console.log(this.caseName)
    console.log(this.isNight)
    console.log(imageUrls.urban.noon[0])
  },
  data: function () {
    return {
      isNight: false,
      peopleNum: -1,
      isPlayingAudio: false
    }
  },
  methods: {
    play: function () {
      if (this.isPlayingAudio) {
        document.getElementById('audio').pause()
      } else {
        document.getElementById('audio').play()
      }
      this.isPlayingAudio = !this.isPlayingAudio
    },
    decreasePeople: function (event) {
      if (this.peopleNum === -1) {
        this.peopleNum = this.peopleMin
      } else if (this.peopleNum <= this.peopleMin) {
        this.peopleNum = this.peopleMax
      } else {
        this.peopleNum--
      }
    },
    increasePeople: function (event) {
      if (this.peopleNum === -1) {
        this.peopleNum = this.peopleMin
      } else if (this.peopleNum >= this.peopleMax) {
        this.peopleNum = this.peopleMin
      } else {
        this.peopleNum++
      }
    },
    changeTime: function (event) {
      this.isNight = !this.isNight
      this.peopleNum = this.peopleMin
      document.getElementById('audio').pause()
      this.isPlayingAudio = false
    }
  },
  computed: {
    tweetHref: function () {
      let temp
      switch (this.caseName) {
        case 'urban':
          temp = imageUrls.urban
          break
        case 'resid':
          temp = imageUrls.resid
          break
        default:
          temp = imageUrls.country
      }
      temp = this.isNight ? temp.night : temp.noon
      if (temp[this.peopleNum - this.peopleMin]) {
        return 'http://twitter.com/intent/tweet?text=いっしょにかえろう。かつての『かえりみち』をカスタムしてみました！あなたも自分の帰り道を作ってみませんか？%20' + temp[this.peopleNum - this.peopleMin].toString() +
        '&via=DP9_Official&hashtags=駒場祭'
      } else {
        return ''
      }
      // return this.peopleNum
    },
    peopleMax: function () {
      switch (this.caseName) {
        case 'urban':
          if (!this.isNight) {
            return 7
          } else {
            return 6
          }
        case 'resid':
          if (!this.isNight) {
            return 5
          } else {
            return 10
          }
        case 'country':
          if (!this.isNight) {
            return 8
          } else {
            return 13
          }
        default:
          return 1
      }
    },
    peopleMin: function () {
      switch (this.caseName) {
        case 'urban':
          if (!this.isNight) {
            return 1
          } else {
            return 1
          }
        case 'resid':
          if (!this.isNight) {
            return 1
          } else {
            return 6
          }
        case 'country':
          if (!this.isNight) {
            return 2
          } else {
            return 9
          }
        default:
          return 1
      }
    },
    imgName: function () {
      switch (this.caseName) {
        case 'urban':
          if (!this.isNight) {
            return 'hito_tokai_' + this.peopleNum
          } else {
            return 'hito_tokai_night_' + this.peopleNum
          }
        case 'resid':
          return 'hito_jutaku_' + this.peopleNum
        case 'country':
          return 'hito_inaka_' + this.peopleNum
        default:
          return ''
      }
    },
    audioName: function () {
      switch (this.caseName) {
        case 'urban':
          if (!this.isNight) {
            return 'oto_tokai_afternoon'
          } else {
            return 'oto_tokai_night'
          }
        case 'resid':
          if (!this.isNight) {
            return 'oto_jutaku_afternoon'
          } else {
            return 'oto_jutaku_night'
          }
        case 'country':
          if (!this.isNight) {
            return 'oto_inaka_afternoon'
          } else {
            return 'oto_inaka_night'
          }
        default:
          return ''
      }
    },
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
