<template>
  <div id="mainapp">
    <link rel="stylesheet" href="/static/style.css">
    <div class="mdl-layout mdl-js-layout mdl-layout--fixed-header">

      <div class="android-header mdl-layout__header mdl-layout__header--waterfall">
        <div class="mdl-layout__header-row">
          <span class="android-title mdl-layout-title">
        
          </span>
          <!-- Add spacer, to align navigation to the right in desktop -->
          <div class="android-header-spacer mdl-layout-spacer"></div>
          <!-- Navigation -->
          <div class="android-navigation-container">
            <nav class="android-navigation mdl-navigation">
              <a class="mdl-navigation__link mdl-typography--text-uppercase" href="https://twitter.com/search?q=%2352WeekChallenge&src=typd">Twitter</a>
              <a class="mdl-navigation__link mdl-typography--text-uppercase" href="https://github.com/bikundo/-52WeekChallenge">Github</a>
            </nav>
          </div>
          <span class="android-mobile-title mdl-layout-title">
            <!-- <img class="android-logo-image" src="/static/images/android-logo.png"> -->
          </span>
        </div>
      </div>

      <div class="android-content mdl-layout__content">
        <a name="top"></a>
        <div class="android-be-together-section mdl-typography--text-center">
          <div class="logo-font android-slogan"></div>
          <div class="logo-font android-sub-slogan"></div>
          <div class="logo-font android-create-character"></div>
        </div>
        <div class="android-customized-section">
          <Calc></Calc>
        </div>


        <footer class="android-footer mdl-mega-footer">
          <div class="mdl-mega-footer--top-section">
            <div class="mdl-mega-footer--right-section">
              <a class="mdl-typography--font-light" href="#top">
                Back to Top
                <i class="material-icons">expand_less</i>
              </a>
            </div>
          </div>

          <div class="mdl-mega-footer--middle-section">
            <p class="mdl-typography--font-light">© 2019</p>
            <p class="mdl-typography--font-light">Some features may not be available in all browsers</p>
          </div>
        </footer>
      </div>
    </div>
  </div>
</template>

<script>
  import Calc from './components/Calc';

  export default {
    name: 'app',
    components: {
      Calc,
    },
  };
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
