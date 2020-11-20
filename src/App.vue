<template>
  <div id="app">
  <header>

    <h1>
      <a href="/">つなげる/わける展</a>
    </h1>
    <nav class="pc-nav">
      <ul>
        <li class="nav-content"><a href="#">かえりみち</a></li>
        <li class="nav-border"></li>
        <li class="nav-content"><a href="#">物体X</a></li>
        <li class="nav-border"></li>
        <li class="nav-content"><a href="#">わける・わけないゲーム</a></li>
        <li class="nav-border"></li>
        <li class="nav-content"><a href="#">アイソメトリックイラスト</a></li>
      </ul>

    </nav>
    <button type="button" class="drawer-toggle drawer-hamburger">
      <a class="menu-trigger" href="#">
        <span></span>
        <span></span>
        <span></span>
      </a>
    </button>
    <nav class="drawer-nav" role="navigation">
      <ul class="drawer-menu">
        <li><a class="drawer-menu-item" href="#">かえりみち</a></li>
        <li class="nav-border"></li>
        <li><a class="drawer-menu-item" href="#">物体X</a></li>
        <li class="nav-border"></li>
        <li><a class="drawer-menu-item" href="#">わける/わけないゲーム</a></li>
        <li class="nav-border"></li>
        <li><a class="drawer-menu-item" href="#">アイソメトリックイラスト</a></li>
      </ul>
    </nav>
  </header>

    <router-view/>
  </div>
</template>

<style lang="scss">
@import url(./assets/style.css);
</style>
