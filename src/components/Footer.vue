<template>
  <footer v-bind:class="[color]">
    <img src="" alt="" class="logo">
    <p class="copyright">
      Copyright (C) designing plus nine. All Rights Reserved.
    </p>
  </footer>
</template>

<style lang="scss" scoped>
@import "../assets/variables.scss";

footer {
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
