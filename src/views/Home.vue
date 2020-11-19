<template>
  <div class="home">
    <Header />
    <section class="fv">
      <div class="fv-logo"></div>
    </section>
    <section class="second">
      <div class="bar"></div>
      <p class="caption">
        授業や飲み会などの遊びがオンラインになったことで、<br>
        「切断」すればいつでも「帰る」ことができるようになった。<br>
        しかしそれはデジタルなもので、<br>
        談笑しつつ三々五々帰っていく余韻は失われた。<br>
        動画、文章など媒体を問わず失われた「帰り道」を再現する。
      </p>
      <div class="bar"></div>
    </section>
    <section class="case urban">
      <div class="bar"></div>
      <div class="img-section">
        <h2 class="case urban">都会</h2>
        <h3 class="case urban">CITY</h3>
        <p class="case urban">
          4限終わり。<br>
          たったひとつ楽しみがあるだけで、<br>
          こんなに足取りの軽くなる、黄金色の世界。<br>
        </p>
        <button class="sound">音声</button>
        <img src="" alt="" class="img-case">
      </div>
      <a href="./case/urban">
        <button class="to-case">
          都会で帰り道を作る
        </button>
      </a>
      <div class="bar"></div>
    </section>
    <section class="case resid">
      <div class="bar"></div>
      <div class="img-section">
        <h2 class="case resid">住宅街</h2>
        <h3 class="case resid">RESIDENTIAL AREA</h3>
        <p class="case resid"> <!-- todo -->
          いつもよりちょっと早い帰路には<br>
          見慣れた制服。<br>
          そっか、君たちが私の後輩なんだね。<br>
        </p>
        <button class="sound">音声</button>
        <img src="" alt="" class="img-case">
      </div>
      <a href="./case/resid">
        <button class="to-case">
          住宅街で帰り道を作る
        </button>
      </a>
      <div class="bar"></div>
    </section>
    <section class="case country">
      <div class="bar"></div>
      <div class="img-section">
        <h2 class="case country">田舎</h2>
        <h3 class="case country">COUNTRYSIDE</h3>
        <p class="case country"> <!-- todo -->
          走る。走る。走る。笑う。<br>
          たったそれだけのことが、<br>
          一番の宝物だった日々が、<br>
          確かにあったんだ。<br>
        </p>
        <button class="sound">音声</button>
        <img src="" alt="" class="img-case">
      </div>
      <a href="./case/country">
        <button class="to-case">
          田舎で帰り道を作る
        </button>
      </a>
      <div class="bar"></div>
    </section>
    <Footer color='green'></Footer>
  </div>
</template>

<script>
// @ is an alias to /src
import Header from '../components/Header'
import Footer from '../components/Footer'

export default {
  name: 'Home',
  components: {
    Header,
    Footer
  }
}
</script>

<style lang="scss">
@import "../assets/variables.scss";

body {
  margin: 0;
  font-family: 'Noto Sans JP', -apple-system, BlinkMacSystemFont, sans-serif;
  font-weight: 500;
}

section.fv {
  height: 90vh;
  background-color: $beige-green;
  background-image: url('../assets/Web_Banner.png');
  background-size: cover;
}

section.second {
  height: 90vh;
  padding: 10vh 32px;
  background-color: $beige-orange;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  justify-content: center;
  .caption {
    margin: 0;
    line-height: 2.2em;
  }
  .bar {
    background-color: $purple;
  }
}

.bar {
  width: 1px;
  height: 80px;
  margin: 48px 0;
}

section.case {
  padding: 20vh 48px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.urban {
  background-color: $purple;
  color: $purple-text;
  .bar {
    background-color: $purple-text;
  }
}

.resid {
  background-color: $pink;
  color: $pink-text;
  .bar {
    background-color: $pink-text;
  }
}

.country {
  background-color: $green;
  color: $green-text;
  .bar {
    background-color: $green-text;
  }
}

</style>
