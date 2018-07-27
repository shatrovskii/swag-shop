<template>
  <section class="container">
    <a href="product/t-shirt"><h1 class="h1 full-height">RtB Swag Shop</h1></a>
    <div class="image-container half-height">
      <div class="background-text"></div>
      <div class="background-text background-text--left"></div>
      <div class="background-text background-text--right"></div>
      <div class="background-text background-text--bottom"></div>
    </div>
    <h1 class="h1 full-height">Some more text</h1>
  </section>
</template>

<script>
import AppLogo from '~/components/AppLogo.vue'

export default {
  components: {
    AppLogo
  }
}
</script>

<style>
.container {
  min-height: 100vh;
  perspective: 1px;
}

.h1 {
  display: flex;
  align-items: center;
  justify-content: center;
}

.links {
  padding-top: 15px;
}

.half-height {
  height: 50vh;
}

.full-height {
  height: 100vh;
}

.image-container {
  position: relative;
  background-image: url("https://realtimeboard.com/blog/wp-content/uploads/2018/05/sa-rtb-14.jpg");
  background-size: contain;
  overflow: hidden;
}

.background-text {
  height: 70px;
  width: 100%;
  background-image: url("~/assets/background.png");
  animation: background-animation 30s linear infinite;
}

.background-text--left {
  position: absolute;
  left: calc(-50% + 35px);
  transform: rotate(-90deg);
  z-index: 1;
}

.background-text--right {
  position: absolute;
  left: calc(50% - 35px);
  transform: rotate(90deg);
  z-index: 1;
}

.background-text--bottom {
  position: absolute;
  transform: rotate(180deg);
  bottom: 0;
}

@keyframes background-animation {
  100% {
    background-position-x: 1636px;
  }
}

</style>

