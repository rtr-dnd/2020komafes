<template>
  <div>
    <Header></Header>
    <h1>{{caseNameJa}}</h1>
    <section class="one">
      <h2>STEP 1</h2>
      <div class="upper-img">
        <p>{{caseNameJa}}での帰り道をカスタマイズしよう</p>
        <button class="sound">音声</button>
      </div>
      <img src="" alt="" class="one">
      <div class="under-img">
        <div class="people">
          <button class="arrow-left">Arrow Left</button>
          <button class="arrow-right">Arrow Right</button>
          <p>人数を変える</p>
        </div>
        <div class="time">
          <p>時間帯を変える</p>
          <button class="arrow-left">Arrow Left</button>
          <button class="arrow-right">Arrow Right</button>
        </div>
      </div>
    </section>
    <section class="two">
      <h2>STEP 2</h2>
      <div class="share-row">
        <button class="twitter">Twitter</button>
        <p>あなたの帰り道で生成されたポストカードをシェアしよう</p>
      </div>
    </section>
    <Footer></Footer>
  </div>
</template>

<style lang="scss" scoped>

</style>

<script>
import Header from '../components/Header'
import Footer from '../components/Footer'

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
    }
  }
}
</script>
