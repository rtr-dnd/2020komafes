<template>
  <div class="home">
    <Header />
    <section class="fv">
      <div class="fv-logo"></div>
    </section>
    <section class="second">
      <p class="caption">
        授業や飲み会などの遊びがオンラインになったことで、<br>
        「切断」すればいつでも「帰る」ことができるようになった。<br>
        しかしそれはデジタルなもので、<br>
        談笑しつつ三々五々帰っていく余韻は失われた。<br>
        動画、文章など媒体を問わず失われた「帰り道」を再現する。
      </p>
    </section>
    <section class="case urban">
      <h2 class="case urban">都会</h2>
      <h3 class="case urban">CITY</h3>
      <p class="case urban">
        4限終わり。<br>
        たったひとつ楽しみがあるだけで、<br>
        こんなに足取りの軽くなる、黄金色の世界。<br>
      </p>
      <button class="sound">音声</button>
      <img src="" alt="" class="img-case">
      <a href="./case/urban">
        <button class="to-case">
          都会で帰り道を作る
        </button>
      </a>
    </section>
    <section class="case resid">
      <h2 class="case resid">住宅街</h2>
      <h3 class="case resid">RESIDENTIAL AREA</h3>
      <p class="case resid"> <!-- todo -->
        4限終わり。<br>
        たったひとつ楽しみがあるだけで、<br>
        こんなに足取りの軽くなる、黄金色の世界。<br>
      </p>
      <button class="sound">音声</button>
      <img src="" alt="" class="img-case">
      <a href="./case/resid">
        <button class="to-case">
          住宅街で帰り道を作る
        </button>
      </a>
    </section>
    <section class="case country">
      <h2 class="case country">田舎</h2>
      <h3 class="case country">COUNTRYSIDE</h3>
      <p class="case country"> <!-- todo -->
        4限終わり。<br>
        たったひとつ楽しみがあるだけで、<br>
        こんなに足取りの軽くなる、黄金色の世界。<br>
      </p>
      <button class="sound">音声</button>
      <img src="" alt="" class="img-case">
      <a href="./case/country">
        <button class="to-case">
          田舎で帰り道を作る
        </button>
      </a>
    </section>
    <footer>
      <img src="" alt="" class="logo">
      <p class="copyright">
        Copyright (C) designing plus nine. All Rights Reserved.
      </p>
    </footer>
  </div>
</template>

<script>
// @ is an alias to /src
import Header from '../components/Header'

export default {
  name: 'Home',
  components: {
    Header
  }
}
</script>
