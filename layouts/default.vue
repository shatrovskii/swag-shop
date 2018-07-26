<template>
  <div>
    <nuxt/>
  </div>
</template>

<style>
html {
  font-family: Gerbera, "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*, *:before, *:after {
  box-sizing: border-box;
  margin: 0;
}

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}

@font-face {
  font-family: 'Gerbera';
  font-style: normal;
  font-weight: normal;
  src: url('https://realtimeboard.com/static/font/Gerbera/Gerbera-Regular.woff2') format('woff2')
}

@font-face {
  font-family: 'ActionCondensedBold';
  src: url('https://realtimeboard.com/blog/wp-content/themes/prod-theme/fonts/action/ActionCondensedBold-Grade1.otf') format('opentype');
  font-weight: normal;
  font-style: normal;
  font-stretched: condensed;
}
</style>

