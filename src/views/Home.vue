<template>
  <div class="home">
    <Header />
    <section class="fv">
      <div class="fv-logo"></div>
    </section>
    <section class="second">
      <div class="bar"></div>
      <div class="img"></div>
      <p class="caption">
        授業や飲み会などの遊びがオンラインになったことで、<br>
        「切断」すればいつでも「帰る」ことができるようになった。<br>
      </p>
      <p class="caption">
        しかしそれはデジタルなもので、<br>
        談笑しつつ三々五々帰っていく余韻は失われた。<br>
      </p>
      <p class="caption">
        動画、文章など媒体を問わず失われた「帰り道」を再現する。
      </p>
      <div class="bar"></div>
    </section>
    <section class="case urban">
      <div class="bar"></div>
      <div class="img-section">
        <h2 class="case urban">都会</h2>
        <h3 class="case eng urban">CITY</h3>
        <p class="case urban">
          4限終わり。<br>
          たったひとつ楽しみがあるだけで、<br>
          こんなに足取りの軽くなる、黄金色の世界。<br>
        </p>
        <div class="sound">
          <img src="../assets/icons/sound-purple.svg" alt="">
        </div>
        <img src="../assets/tokai1_4.png" alt="" class="img-case">
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
        <h3 class="case eng resid">RESIDENTIAL <br> AREA</h3>
        <p class="case resid"> <!-- todo -->
          いつもよりちょっと早い帰路には<br>
          見慣れた制服。<br>
          そっか、君たちが私の後輩なんだね。<br>
        </p>
        <div class="sound">
          <img src="../assets/icons/sound-pink.svg" alt="">
        </div>
        <img src="../assets/jutaku1_4.png" alt="" class="img-case">
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
        <h3 class="case eng country">COUNTRYSIDE</h3>
        <p class="case country"> <!-- todo -->
          走る。走る。走る。笑う。<br>
          たったそれだけのことが、<br>
          一番の宝物だった日々が、<br>
          確かにあったんだ。<br>
        </p>
        <div class="sound">
          <img src="../assets/icons/sound-green.svg" alt="">
        </div>
        <img src="../assets/inaka1_4.png" alt="" class="img-case">
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

.eng {
  font-family: 'Fredoka One', -apple-system, BlinkMacSystemFont, sans-serif;
}

section.fv {
  height: 90vh;
  background-color: $beige-green;
  background-image: url('../assets/Web_Banner.png');
  @media screen and (max-width: 769px){
    background-image: url(../assets/Phone_Main.png);
  }
  background-size: cover;
}

.fv-logo {
  width: 80%;
  height: 100%;
  max-width: 640px;
  background-image: url(../assets/logo.svg);
  background-repeat: no-repeat;
  background-size: contain;
  background-position: center;
  margin: 0 auto;
}

section.second {
  position: relative;
  height: 90vh;
  padding: 10vh 32px;
  background-color: $beige-orange;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  justify-content: center;
  @media screen and (max-width: 769px){
    height: auto;
    padding: 10vh 48px;
  }

  .caption {
    margin: 0;
    line-height: 2.2em;
    position: relative;
    z-index: 1;
    @media screen and (max-width: 769px){
      margin: 32px 0;
    }
  }
  .bar {
    position: relative;
    z-index: 1;
    background-color: $purple;
  }
  .img {
    position: absolute;
    z-index: 0;
    width: 70%;
    height: 100%;
    top: 50%;
    left: 50%;
    transform: translateX(-50%) translateY(-50%);
    background-repeat: no-repeat;
    background-position: center;
    background-size: contain;
    background-image: url(../assets/Web_Back.svg);
    @media screen and (max-width: 767px){
      background-image: url(../assets/Phone_Back.svg);
    }
  }
}

.bar {
  width: 1px;
  height: 120px;
  margin: 48px 0;
}

section.case {
  padding: 20vh 48px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;

  @media screen and (max-width: 769px){
    padding: 10vh 48px;
  }

  .img-section {
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    width: 80%;
    max-width: 640px;
    margin: 48px 0 120px 0;

    img.img-case {
      width: 100%;
      display: block;
    }

    h2 {
      background-color: transparent;
      position: absolute;
      margin: 0;
      font-size: 96px;
      font-weight: 900;
      line-height: 1.0em;
    }
    h3 {
      background-color: transparent;
      position: absolute;
      margin: 0;
      line-height: 1.0em;
      font-size: 56px;
      font-weight: 200;
    }
    p {
      background-color: transparent;
      position: absolute;
      margin: 0;
      line-height: 2.5em;
      font-size: 14px;
    }
    .sound {
      position: absolute;
      border: none;
      img {
        width: 48px;
      }
      &:hover {
        opacity: 0.4;
      }
    }
  }
  button.to-case {
    cursor: pointer;
    transition: 0.3s;
    font-weight: 500;
    border-radius: 8px;
    border: 2px solid;
    box-shadow: none;
    padding: 16px 40px;
  }
}

.urban {
  background-color: $purple;
  color: $purple-text;
  border-color: $purple-text;
  .bar {
    background-color: $purple-text;
  }
  button {
    background-color: transparent;
    color: $purple-text;
    border-color: $purple-text;
    &:hover {
      background-color: $purple-text;
      color: $purple;
    }
  }
  h2 {
    top: 0;
    left: 0;
    transform: translateX(-40%) translateY(-50%);
  }
  h3 {
    top: 50%;
    left: 0;
    font-size: 80px;
    transform: rotate(90deg) translateY(120%);
  }
  p {
    right: 0;
    bottom: 0;
    text-align: left;
    transform: translateX(30%) translateY(30%);
  }
  .sound {
    top: 0;
    right: 0;
    transform: translateX(100%) translateY(-100%);
  }
}

.resid {
  background-color: $pink;
  color: $pink-text;
  border-color: $pink-text;
  .bar {
    background-color: $pink-text;
  }
  button {
    background-color: transparent;
    color: $pink-text;
    border-color: $pink-text;
    &:hover {
      background-color: $pink-text;
      color: $pink;
    }
  }
  h2 {
    bottom: 0;
    right: 0;
    text-align: right;
    transform: translateX(30%) translateY(30%);
  }
  h3 {
    top: 0;
    transform: translateY(-30%);
  }
  p {
    text-align: right;
    left: 0;
    bottom: 0;
    transform: translateX(-20%) translateY(20%);
  }
  .sound {
    top: 0;
    left: 0;
    transform: translateX(-150%);
  }
}

.country {
  background-color: $green;
  color: $green-text;
  border-color: $green-text;
  .bar {
    background-color: $green-text;
  }
  button {
    background-color: transparent;
    color: $green-text;
    border-color: $green-text;
    &:hover {
      background-color: $green-text;
      color: $green;
    }
  }
  h2 {
    writing-mode: vertical-rl;
    letter-spacing: 0.1em;
    left: 0;
    bottom: 0;
    transform: translateX(-50%);
  }
  h3 {
    left: 0;
    right: 0;
    text-align: right;
    bottom: 0;
    transform-origin: bottom right;
    transform: rotate(90deg) translateY(60%);
  }
  p {
    bottom: 0;
    transform: translateY(50%);
    line-height: 2.0em !important;
  }
  .sound {
    left: 0;
    top: 0;
    transform: translateX(-100%) translateY(-100%);
  }
}

</style>
