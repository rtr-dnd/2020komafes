<template>
  <footer v-bind:class="[color]">
    <img v-if="color === 'green'" src="../assets/dp9logo-green.svg" alt="" class="logo">
    <img v-if="color === 'pink'" src="../assets/dp9logo-pink.svg" alt="" class="logo">
    <img v-if="color === 'purple'" src="../assets/dp9logo-purple.svg" alt="" class="logo">
    <p class="copyright">
      Copyright (C) designing plus nine. All Rights Reserved.
    </p>
  </footer>
</template>

<style lang="scss" scoped>
@import "../assets/variables.scss";

footer {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 48px 64px;
  img {
    display: block;
    height: 40px;
  }
  .copyright {
    font-size: 13px;
    text-align: right;
  }
  @media screen and (max-width: 769px){
    flex-direction: column;
    padding: 48px 12px;
    .copyright {
      text-align: center;
      margin: 0;
      padding-top: 32px;
    }
  }

  &.green {
    background-color: $green;
    color: $green-text;
  }
  &.purple {
    background-color: $purple;
    color: $purple-text;
  }
  &.pink {
    background-color: $pink;
    color: $pink-text;
  }
}

</style>

<script>
export default {
  name: 'Header',
  props: {
    color: String
  }
}
</script>
